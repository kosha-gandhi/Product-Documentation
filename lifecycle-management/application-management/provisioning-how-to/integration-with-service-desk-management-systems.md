# Integration with Service Desk Management Systems

### Overview

This page outlines the process for integrating your Service Desk platform with Cymmetri. This integration will streamline workflows, enhance communication, and improve overall service management.

#### Prerequisites

Before beginning the integration, ensure you have:

* Administrative access to both the Service Desk and Cymmetri.
* API keys or authentication tokens for both platforms.
* Backup of existing configurations, if necessary.

### Step 1: Configure Your Service Desk

1. **Login to Your Service Desk**
   * Access your Service Desk portal and log in with your admin credentials.
2. **Access API Settings**
   * Navigate to **Settings** > **API**.
   * Enable API access if it is not already enabled.
   * Generate an API key if you do not have one.
3. **Record API Endpoint**
   * Note the API endpoint URL (e.g., `https://your-servicedesk.com/api/v1/`).

### Step 2: Configure Cymmetri

1. **Login to Cymmetri**
   * Go to your Cymmetri dashboard and log in as an administrator.
2. **Access Integration Settings**
   * Navigate to **Identity Hub** > **Applications**.
   * Click on **Add New Application**.
3. **Select Service Desk**
   * Choose your specific Service Desk platform from the list of available integrations. Cymmetri has ready connectors for ServiceNow, Atlassian (Jira), Fresh Service, etc.&#x20;
4. **Enter API Details**
   * **API URL**: Enter the API endpoint noted from your Service Desk.
   * **API Key**: Paste the API key generated in your Service Desk.
5. **Test Connection**
   * Click on **Test Connection** to ensure Cymmetri can successfully communicate with your Service Desk.
   * If successful, proceed to the next step. If not, double-check your API settings.

### Step 3: Map Data Fields

1. **Field Mapping using Policy Map**
   * Map relevant fields between your Service Desk and Cymmetri. Common fields to consider include:
     * **Ticket ID**
     * **Status**
     * **Priority**
     * **Assignee**
     * **Comments**
2. **Configure Sync Settings**
   * Decide on the synchronization direction (one-way or two-way).
   * Set the sync frequency (e.g., real-time, hourly, daily).

## Integration&#x20;

To integrate a service desk with Cymmetri for handling requests such as user provisioning for applications like CRM, the process involves leveraging Cymmetri’s Identity Governance and Administration (IGA) platform capabilities to manage the lifecycle of requests while synchronizing the ticketing and provisioning process. Here’s a brief description of how to manage this integration:

### &#x20;1. Integration with Service Desk (Zoho Desk, ServiceNow):

&#x20;The integration between Cymmetri and service desks like Zoho Desk or ServiceNow typically uses APIs or webhooks to enable communication between the two systems. The integration can be broken down into the following steps:&#x20;

#### Request Creation in Service Desk:

• A user submits a request for access to an application, like CRM, via the service desk portal.

• This request triggers an API call or webhook from the service desk to Cymmetri, initiating the workflow in Cymmetri for provisioning.

#### Provisioning Workflow in Cymmetri:

• Cymmetri receives the request and starts the approval workflow, following its defined governance policies.

• Multiple layers of approval can be enforced, such as managerial, application owner, or compliance approval, based on pre-defined rules.

• Once the request is approved, Cymmetri will provision the user access to the requested application (in this case, CRM).

#### Ticket Closure in Service Desk:

• Once the provisioning is successful, Cymmetri sends an API response or webhook back to the service desk, indicating that the provisioning process is complete.

• The service desk system then automatically updates the ticket status to “Closed.”

### 2. Managing Governance in Cymmetri for Service Desk Integration:

Governance is crucial in ensuring the proper approval, auditing, and compliance are maintained throughout the request and provisioning lifecycle. Here’s how governance can be managed:

#### Access Request Governance:

• Define governance rules and policies for access requests originating from the service desk.

• Set up role-based access controls (RBAC) to ensure that users can only request access to applications they are entitled to.

• Configure workflows in Cymmetri to enforce approval chains before provisioning occurs. For instance, managerial approval, application owner approval, and segregation of duties (SoD) checks can be part of the process.

#### Approval and Audit Trails:

• Cymmetri maintains a detailed audit trail of each request. This ensures that all approvals, denials, or escalations are documented, providing an audit trail for governance and compliance reporting.

• Approval workflows should be automated and governed by pre-defined policies such as the least privilege principle or SoD rules, which prevent conflicting roles from being assigned.

#### Policy Violation Management:

• Cymmetri can be configured to check for policy violations before completing the provisioning. For example, if a user requests access to a role that creates an SoD violation, Cymmetri can trigger a violation notification and require additional approvals or corrective actions before the process can move forward.

#### Automated De-provisioning:

• Cymmetri ensures that de-provisioning is part of the governance process. If a user’s access is no longer required, a de-provisioning request can be triggered either automatically or through the service desk. This will update both systems (Cymmetri and service desk) accordingly.

#### Compliance and Reporting:

• Regular audits can be run through Cymmetri to ensure compliance with governance policies. Reports can show who has been granted access, what approvals were made, and if there were any violations or exceptions.

• Cymmetri can generate compliance reports for auditing, allowing organizations to meet regulatory requirements like SOX or GDPR.

### 3. Technical Workflow Example:&#x20;

#### Step 1: User Requests Application Access (CRM)&#x20;

• User logs into the service desk (e.g., Zoho Desk or ServiceNow) and submits a request for CRM application access.

• The service desk creates a request ticket with relevant details, such as the user’s name, department, requested application, and purpose.&#x20;

#### Step 2: Request Forwarded to Cymmetri&#x20;

• The service desk system calls Cymmetri’s API or triggers a webhook to submit the request into Cymmetri.

• Cymmetri initiates the appropriate access request workflow, considering any SoD checks or policy violations.

#### &#x20;Step 3: Approval Workflow in Cymmetri&#x20;

• The request is sent through an approval process within Cymmetri based on the organization’s policies. This may involve managerial approval, compliance checks, or application owner approval.

• If any SoD violations are detected, Cymmetri can block the request, notify the necessary stakeholders, and propose alternate access solutions.&#x20;

#### Step 4: Provisioning in Cymmetri&#x20;

• Once the request is approved, Cymmetri provisions access to the CRM application via its integration with the organization’s IAM system.

• Cymmetri ensures that appropriate roles or permissions are granted according to the approved request.&#x20;

#### Step 5: Notification and Ticket Closure&#x20;

• Once provisioning is complete, Cymmetri sends a notification back to the service desk via API or webhook.

• The service desk automatically closes the request ticket, notifying the user that their access has been granted.&#x20;

#### Step 6: Audit and Compliance Reporting&#x20;

• Cymmetri logs all actions, approvals, and violations, ensuring a detailed audit trail.

• Governance reports can be generated to meet compliance standards and verify that all requests followed organizational policies.&#x20;

### 4. Key Governance Features in Cymmetri for Service Desk Integration:&#x20;

• Policy Definition: Define access policies and approval workflows for requests.

• Role-Based Access Control (RBAC): Assign roles and permissions based on user attributes, and automate provisioning accordingly.

• Segregation of Duties (SoD) Enforcement: Prevent conflicting roles from being granted by ensuring compliance with SoD policies.

• Audit and Compliance Reporting: Keep detailed logs of all actions, approvals, and violations for audit purposes.

• Automated Lifecycle Management: Automate provisioning and de-provisioning workflows while maintaining governance controls.&#x20;

This integration ensures smooth communication between the service desk and Cymmetri, enabling automated provisioning with governance controls, reducing the manual effort required to manage access requests, and ensuring compliance with policies.

### Step 5: Testing the Integration

1. **Create Test Tickets**
   * Create several test tickets in your Service Desk.
   * Confirm that these tickets are reflected in Cymmetri as expected.
2. **Update Test Tickets**
   * Modify the status or comments of the test tickets in either system and check if the changes sync properly.

### Troubleshooting

* **Connection Issues**: Double-check API keys and endpoint URLs. Ensure both systems are operational.
* **Data Sync Problems**: Review field mappings and sync settings. Check integration logs for errors.
