# Pending Workflows

The Pending Workflows List page provides a consolidated view of all ongoing workflows awaiting approval or rejection.&#x20;

The comprehensive snapshot enables administrators to quickly identify pending tasks, their current status, and the associated contextual details. This tool provides at-a-glance insights into each workflow's essential information, including Topic, Workflow Level, Status, Group Name, Requestor, and Current Assignee.&#x20;

By providing a centralized location for pending workflows, this page allows Administrators to effortlessly track the progression of tasks, ensuring timely reviews and approvals.&#x20;

<figure><img src="../../.gitbook/assets/image (454).png" alt=""><figcaption></figcaption></figure>

### Reassign Workflow

One of the very important actions provided on the Pending workflow page is Reassign Workflow. This option enables administrators to delegate the approval request to another user in cases when the current approver is not available due to various circumstances.

<figure><img src="../../.gitbook/assets/image (801).png" alt=""><figcaption></figcaption></figure>

For reassigning the workflow to another approver, the user needs to click on the reassign button and then select the new approver on the pop-up window, as shown below:

<figure><img src="../../.gitbook/assets/image (802).png" alt=""><figcaption></figcaption></figure>

### Unclaimed Workflow with note in Pending Workflow

An "Unclaimed" status for a workflow indicates that the task is awaiting assignment to a specific user. On the Pending Workflows page, a workflow with this status shows UNCLAIMED in the Current Assign column. Hovering over this status displays a tooltip with the message: "Pending claim with group, grade, user list, or no approver found. See details for actual assignment."

Display Behavior

* Current Assign = UNCLAIMED
* Note = "Pending claim with group, grade, user list, or no approver found. See details for the actual assignment in Cymmetri.”

<figure><img src="../../.gitbook/assets/unknown (36).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/unknown (37).png" alt=""><figcaption></figcaption></figure>

**Pending Claim with Group**

In this scenario, a workflow is assigned to a specific approval group. However, since no individual user within that group has taken ownership of the task yet, it remains unclaimed. The Current Assign column displays UNCLAIMED, while the Group Name column explicitly shows the name of the group it is assigned to.

<figure><img src="../../.gitbook/assets/unknown (38).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/unknown (39).png" alt=""><figcaption></figcaption></figure>

**Pending Claim with Userlist**

This status occurs when a workflow is directed to a predefined list of specific users. The workflow remains UNCLAIMED because none of the users on the list has yet claimed it. The task will only move out of this state once a user from the specified list accepts the assignment or if it is manually reassigned.

<figure><img src="../../.gitbook/assets/unknown (40).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/unknown (41).png" alt=""><figcaption></figcaption></figure>

**Pending Claim with No Approver Found**

This is an error state where the system fails to identify a valid approver for the workflow. This can happen if the approval rules are misconfigured and no group, grade, or user list is mapped to the request. Since there is no one to claim the task, it remains UNCLAIMED until an administrator manually reassigns it or corrects the underlying approval configuration.

<figure><img src="../../.gitbook/assets/unknown (42).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/unknown (43).png" alt=""><figcaption></figcaption></figure>
