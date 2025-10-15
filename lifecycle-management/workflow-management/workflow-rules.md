# Workflow Rules

Custom workflows can be configured and customized further by creating workflow rules.These rules help defining conditions that trigger the workflow. Also these rules enable administrator to reuse a workflow grid for multiple processes and events which further reduces the reduntant effort an administrator needs to put.&#x20;

### Creating a Workflow Rule

To create Workflow Rules Navigate to **Products -> Lifecycle Management -> Workflow -> Rules** and click on the **+Add New** button

<figure><img src="../../.gitbook/assets/image (592).png" alt=""><figcaption></figcaption></figure>

On the Workflow Rule Creation page as shown below, Following details need to be provided:

<figure><img src="../../.gitbook/assets/image (593).png" alt=""><figcaption></figcaption></figure>

#### **Attributes:**

**Name:** (Mandatory)Name of the Worflow Rule

**Workflow:** (Mandatory) Need to select the custom workflow for which the rule will be applicable

**Event:** (Mandatory) Select event triggering the workflow

<figure><img src="../../.gitbook/assets/image (846).png" alt=""><figcaption></figcaption></figure>

Mentioned below are its descriptions:

1. **Application Provisioning:** When an application is assigned to a user, this type od workflow is triggered to approve the provisioning process.&#x20;
2. **Application Deprovisioning:** When an application is unassigned from a user, this type of workflow is triggered to approve the deprovisioning process.
3. **User Creation:** When a new user is created in Cymmetri, this type of  workflow is triggered to approve the user creation process.&#x20;
4. **Workflow Setup:** This type of workflow is triggered on the creation, updating, or deletion of mapped workflow configurations and their associated rules. It ensures that any changes to the workflow setup are reviewed and approved, maintaining the integrity and effectiveness of the workflow processes.
5. **Application Role:** When an application role is created, updated, or deleted, this type of workflow is triggered to approve the changes. This ensures that the roles are managed correctly and that any modifications are reviewed and authorized.
6. **Application Update:** When an application menu action or form submission is performed by a user, this type of workflow is triggered to approve the application update.&#x20;
7. **Decommission Device:** When a device is scheduled for deletion, this type of workflow is triggered to approve the decommissioning process. This ensures that the device is properly removed from the system and that any associated data or configurations are handled appropriately.
8.  **SOD Violation:** This workflow would be triggered for any SOD Violation and for taking appropriate action upon the violation. The screenshot below shows a workflow configured for this case

    <figure><img src="../../.gitbook/assets/image (914).png" alt=""><figcaption></figcaption></figure>

**Description:** (Optional) General description of the rule can be provided here for further understanding of the working of the rule

#### **Conditions:**&#x20;

Conditions and filters can be added for country, department, designation, login pattern, user type, application, application role, and workflow depending upon the event selected

<figure><img src="../../.gitbook/assets/image (594).png" alt=""><figcaption></figcaption></figure>

Multiple conditions can be combined using AND/ OR operators

<figure><img src="../../.gitbook/assets/image (782).png" alt=""><figcaption></figcaption></figure>

Conditions can also be grouped to evaluate to true or false as a group

<figure><img src="../../.gitbook/assets/image (783).png" alt=""><figcaption></figcaption></figure>

#### Dynamic routing

Meta conditions can be added for application events if meta values are added for applications.

For example, if the user's grade is a certain value, then the approval steps can be added or bypassed for access approval. Similarly, if the user's custom attribute is matched then approver associations can be changed dynamically. Other parameters that can be used are risk score of the user or checking of SoD policy violation.&#x20;
