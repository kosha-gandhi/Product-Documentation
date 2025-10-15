# Workflow Configuration

Workflows may be configured for a number of use cases in the Cymmetri Identity Platform, primary among them being for assigning application to a user (provisioning), unassigning application to a user (deprovisioning), and running reconciliation campaigns.

## Configuring Workflows in Cymmetri Identity Platform

Workflows in Cymmetri Identity Platform may be configured for a predefined stages of approval, (these number stages are configurable)

<figure><img src="../../.gitbook/assets/image (803).png" alt=""><figcaption></figcaption></figure>

For each stage, the administrator may select one of the following options -&#x20;

**User** - A particular user may approve workflow request at this stage.

**Group** - A user belonging to the selected Group may approve Workflow request at this stage.

**Reporting Manager** - The reporting manager of the user for which the approval is to be provided may approve the workflow request at this stage.

**User List** - A list of preselected users, these users receive the claims request and one of these users may approve the workflow. This can be used to define custom set of approver associations such as application owners, administrators, etc.&#x20;

**Grade** - A list of users that fall in the grade range selected

\
Click on save to save the workflow.

<figure><img src="../../.gitbook/assets/image (805).png" alt=""><figcaption></figcaption></figure>

### Access Request Escalation Policy

Cymmetri allows flexible workflow configuration for managing closure of access requests in time bound manner. In case of escalation scenario, the next in line reporting manager will be automatically escalated based on turn around time definition for the particular workflow step. The relevant users will be alerted through email notification of the escalation of such requests.&#x20;

If no escalation is defined, Cymmetri will automatically mark the request as rejected to end the request cycle. Cymmetri will alert the user of the automatic rejection via email notification.&#x20;

By default Cymmetri workflows are configured to escalate an incoming request to the reporting manager in case the alternate approver is not defined or the workflow is of group approver principle.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXfUxcxaX2ZSCHMvsxrQ0Ws7iKxHLtz9zDLVdjyX7lJeUmoZZZtFPDtdrCP6aRGreJot2zmfvN8Vi5FoyvUhTEAHwwADKH-KlRYIfbqgZH3dILvUcy_UqgVi7pIMOOUp2GEUEBmO90OgGD_BKXRCy8yC4nsg3-abjioPbM4Ba_eN7V6YOAMiz3A?key=ES3-gdOFgPh8dn0zAQKG8w" alt=""><figcaption></figcaption></figure>

In the case if the request is not attended to then it retires as per Turn around time defined. setting it to 0 means it will never retire.

To observe how to workflow runs in action, refer [Inbox](../../my-workspace/how-to-use-the-my-workspace/inbox.md)
