# AMAYA

AMAYA is Cymmetri's no-code/low-code provisioning tool designed to simplify and automate user identity and access management. It allows administrators to create, manage, and automate user provisioning workflows for various target systems (e.g., Slack, Azure, ServiceNow) without requiring extensive coding knowledge. The platform's core functionality is to manage the full lifecycle of user identities and their roles through a series of configurable operations, primarily by leveraging REST API endpoints.

The AMAYA application within Cymmetri is designed to facilitate the provisioning of users and groups to various target systems through a series of configurable operations. This application supports a variety of operations to manage the lifecycle of user identities, including testing a connection to the target system, syncing, searching, creating, updating, deleting, and managing roles.

#### Configuring the Amaya Application in Cymmetri&#x20;

1. Navigate to Applications → Add New → Create from Scratch.
2. Search for and select "Amaya."

<figure><img src="../../../.gitbook/assets/image (34).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (35).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (36).png" alt=""><figcaption></figcaption></figure>

### **Application Provisioning**

The **Application Provisioning** interface for AMAYA is divided into several tabs:

#### **User Configuration**

Let's you configure the various user identity operations quickly and without coding

<figure><img src="../../../.gitbook/assets/image (889).png" alt=""><figcaption></figcaption></figure>

This interface allows administrators to configure and manage how users and groups are provisioned to or from target systems like Slack, Azure, ServiceNow, etc.

### Server Configuration

1. In the Server Configuration panel, input the IP address and other details for the Connector server.

<figure><img src="../../../.gitbook/assets/image (37).png" alt=""><figcaption></figcaption></figure>

2. Save the configuration. A "Provisioning Configuration Successful" message will confirm that the connection profile has been established.

<figure><img src="../../../.gitbook/assets/image (38).png" alt=""><figcaption></figcaption></figure>

3. Test Operation (GET All Users) This step validates the connection and payload structure.

* Import the GET /api/now/table/sys\_user cURL command into the Test Operation slot.

<figure><img src="../../../.gitbook/assets/image (39).png" alt=""><figcaption></figcaption></figure>

* Append ?sysparm\_limit=10 to limit the response to a manageable size (10 users).

<figure><img src="../../../.gitbook/assets/image (40).png" alt=""><figcaption></figcaption></figure>

* Run the request. Verify that the response is a 200 OK and contains an array of ten user objects.

<figure><img src="../../../.gitbook/assets/image (41).png" alt=""><figcaption></figcaption></figure>

* Designate the response array as the result and the unique identifier field, sys\_id, as the Unique ID Key.

<figure><img src="../../../.gitbook/assets/image (42).png" alt=""><figcaption></figcaption></figure>

**Synchronization Operation This operation seeds the policy mapping for attribute synchronization.**

* Paste the validated cURL command into the Sync Operation → cURL Import field.

<figure><img src="../../../.gitbook/assets/image (44).png" alt=""><figcaption></figcaption></figure>

* Re-identify the result and sys\_id fields.

<figure><img src="../../../.gitbook/assets/image (42).png" alt=""><figcaption></figcaption></figure>

* Save the configuration and click Generate Policy Mapping. This launches the automatic attribute mapping wizard.

**Automatic Policy Mapping The wizard scans the sample user data and presents a mapping interface.**

* Source Attribute (ServiceNow): The field name from the ServiceNow response.
* Destination Attribute (Cymmetri): The corresponding Cymmetri field.

For example:

* user\_name maps to login
* first\_name maps to firstName
* email maps to email
* sys\_id maps to the User Principal, which is the mandatory identifier.

You can uncheck irrelevant fields to create a lean and precise mapping.\


<figure><img src="../../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

#### **CRUD Operations Configuration**

**Create User Operation:**

Endpoint: POST /api/now/table/sys\_user

<figure><img src="../../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

* Body Template: A JSON payload that maps Cymmetri user attributes to ServiceNow fields. Cymmetri’s built-in JSON validation and beautification tools ensure the payload is correctly formatted.

For example:

<figure><img src="../../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

Validate –

Role Provisioning: An optional second node, Assign Role, can be added to the flow. This node consumes the sys\_id returned from the initial user creation to assign a role

<figure><img src="../../../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

Role assign another node.

<figure><img src="../../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

**Role Assignment and Unassignment**

**Role Assignment Flow Since ServiceNow handles roles as a separate table, the connector uses a two-node flow:**

* Node 1 (Create User): Creates the user and captures the sys\_id as ${UID}.

<figure><img src="../../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

* Node 2 (Assign Role): Makes a POST call to /api/now/table/sys\_user\_role with a body that links the user (${UID}) and the role (${\_role}).

<figure><img src="../../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

**Update User Operation**

To update an existing user, the system leverages the same attribute mapping used for user creation. However, the API endpoint is modified to include the user's unique identifier.

* API Endpoint: PUT /api/now/table/sys\_user/${UID}
* Method: PUT
* Purpose: This request updates an existing user record. The ${UID} variable, which is an alias for the user's sys\_id in ServiceNow, ensures that the specific user record is targeted. The request body contains the updated user attributes (e.g., first name, email, department), allowing for partial or full updates to the user's profile.

<figure><img src="../../../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

**Delete User Operation**

Deleting a user is a streamlined process that requires only the user's unique identifier.

* API Endpoint: DELETE /api/now/table/sys\_user/${UID}
* Method: DELETE
* Purpose: This request permanently removes a user record from ServiceNow. The DELETE operation automatically handles the removal of all associated data, including any roles linked to the user's account.

<figure><img src="../../../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

#### Role-Based Workflows

Since ServiceNow manages user-to-role relationships in a separate table, the Cymmetri connector uses multi-node flows to handle these operations accurately.

**Role Assignment Flow**

This two-step process ensures a role is correctly assigned to a user immediately after the user account is created.

1. Node 1: Create User
2. Action: A POST request creates the new user account in ServiceNow.
3. Output: The sys\_id of the newly created user is captured and stored as the variable ${UID} for subsequent use.
4. Node 2: Assign Role
5. Action: A POST request is made to the sys\_user\_role table, which manages user-role relationships.
6. API Endpoint: POST /api/now/table/sys\_user\_role

Request Body: The request body formally links the user and the role:\
JSON\
{

&#x20; "user": "${UID}",

&#x20; "role": "${\_role}"

}

* Purpose: This step assigns a specific role to the user, identified by the ${\_role} variable, which is sourced from a pre-loaded CSV file containing over 200 role IDs within Cymmetri.

<figure><img src="../../../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

**Role Unassignment Flow**

This more complex three-node process is required because ServiceNow needs the specific sys\_id of the role assignment record to delete it, rather than just the user or role sys\_id.

1. Node 1: Fetch Assignment ID
2. Action: A GET request queries the sys\_user\_role table to find the specific assignment record.
3. API Endpoint: GET /api/now/table/sys\_user\_role?sysparm\_query=role=${\_role}^user=${UID}
4. Output: The system captures the sys\_id of the role assignment record and stores it as the variable ${roleAssignmentID}.

<figure><img src="../../../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

2. Node 2: Remove Role
   1. Action: A DELETE request is made to the sys\_user\_role table to remove the role assignment.
   2. API Endpoint: DELETE /api/now/table/sys\_user\_role/${roleAssignmentID}
   3. Purpose: This final step explicitly removes the role from the user by using the unique identifier of the assignment&#x20;

<figure><img src="../../../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

#### Advanced Workflow and Data Transformation

This section formalizes the advanced features of the Cymmetri-Amaya integration.

**Multi-Role Support**&#x20;

This feature enables the synchronization of user roles from a connected application (e.g., ServiceNow) into Cymmetri.

* Synchronize Roles: The connector can pull and map user roles from the source system. In Cymmetri, these synchronized roles are typically categorized under a \_ROLE\_ object.
* Assign Roles: The system can bring users in along with their assigned roles, ensuring permissions are accurately reflected in Cymmetri's Identity Hub. This eliminates the need for manual role assignments after user provisioning.

<figure><img src="../../../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

**Condition Node**&#x20;

A Condition Node introduces conditional logic, allowing the workflow to take different paths based on specific criteria.

* Example: A condition can check for a user's type, like usertype:emp (for "employee"). If the condition is met, the workflow follows one path; if not, it follows another. This is crucial for applying different provisioning policies to different types of users (e.g., employees vs. contractors).

<figure><img src="../../../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

**Transformational Node**

A Transformational Node is a powerful tool for manipulating and standardizing data within the workflow. It's used to modify or create data fields based on existing response data from an API call.

* Purpose: The primary use is to convert raw data into a format required by another system. For example, it can be used to generate an email address from a user's employee code.
* Example: An API response might contain an emp\_code field. The Transformational Node can take this value and append a domain to it to create an email address.
* Placeholders: The node uses placeholders (e.g., ${emp\_code}) to refer to specific data attributes from the API response. These placeholders hold the data corresponding to the attribute, making it easy to reference and transform.

<figure><img src="../../../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>

All identity management operations—including user synchronization, creation, updates, and role assignments—are built using a combination of the core nodes mentioned above.

Sync Operation (User Pull): The sync operation uses an API Node to perform a GET request, an Iterator Node to process the list of users returned, and Transformational or Condition Nodes to format the data and apply business logic.

<figure><img src="../../../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

* Create Operation: This operation uses an API Node with a POST request to create a user, followed by Transformational Nodes to format the payload and potentially Condition Nodes for approval workflows.

<figure><img src="../../../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

* Update Operation: Similar to the create operation, it uses an API Node with a PUT or PATCH request, with the same supporting nodes.

<figure><img src="../../../.gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>

Delete Operation: This uses an API Node with a DELETE request, typically a streamlined workflow

<figure><img src="../../../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>

* Role Assign/Unassign: These are multi-node workflows that use a series of API Nodes for creating or deleting role assignments, often including Condition Nodes for validation.

<figure><img src="../../../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>

### **AMAYA Key Operations**&#x20;

* **Test Operation**: This operation is used to test the configuration with the target system. It ensures that the setup is correct and that the AMAYA application can communicate with the target system.
* **Sync Operation**: This operation is used to synchronize users or groups from the target system. It ensures that the user/group data in Cymmetri is consistent with the data in the target system.
* **Search Operation**: This operation allows administrators to search for users or groups in the target system, making it easier to find specific entities.
* **Create Operation**: This operation is used to create users or groups in the target system based on the information in Cymmetri.
* **Update Operation**: This operation allows for updating the details of existing users or groups in the target system, ensuring that changes made in Cymmetri are reflected accurately.
* **Delete Operation**: This operation is used to delete users or groups from the target system, removing access or decommissioning identities as required.
* **Role Assign Operation**: This operation assigns roles to users or groups in the target system, helping to manage permissions and access levels.
* **Role Unassign Operation**: This operation unassigns roles from users or groups in the target system, removing permissions as necessary.

**Quick Setup with Predefined Templates**

The second image shows the **Quick Setup** screen, which provides predefined templates for popular applications. These templates simplify the process of setting up provisioning by offering pre-configured settings for the following applications:

* **Slack**
* **ServiceNow**
* **HubSpot**
* **Azure**
* **AWS Identity Center**
* **Zoho Expenses**
* **Zoho Books**
* **Zoho CRM**
* **Zoho Desk**

Administrators can quickly start with these templates, which have standard configurations, and customize them as needed to suit their specific requirements. The search function at the top allows users to find other applications if the needed one is not listed among the predefined templates.

**Hook Configurations**\
If the administrator needs to write some custom action before and/or after provisioning the application, that can be enabled by configuring web hooks, as shown in the Hook Configuration. The configuration supports a PRE and a POST HOOK for triggering custom code before and/or after provisioning of the application. Refer to webhooks [here](../../configuring-webhooks.md)

<figure><img src="../../../.gitbook/assets/image (895).png" alt=""><figcaption></figcaption></figure>
