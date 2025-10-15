# Inbox

The Cymmetri application workflow mechanism is used to enforce approval of users' access requests for the purpose of right-user-getting-correct-access. At the same time, providing a history of all such requests and their approvals ensures accurate reporting. &#x20;

The Cymmetri Inbox section allows users to view and approve the access requests for other Cymmetri users. Apart from user access approval requests, the user can also view the status of their own access requests under the My Requests section.  Let's have a detailed understanding of each section:

## Requests &#x20;

The Requests section under Inbox lists the application access requests raised by other Cymmetri users. &#x20;

#### Requesting an Application&#x20;

Cymmetri users can request access to applications not automatically assigned to them. These requests for application access may not always require approval. In certain cases, the access request will be automatically applied as there is no approval workflow configured by the Cymmetri Administrator. But in cases where an approval is needed, a workflow request is triggered, and this request process is managed from **My Access > Request** section. &#x20;

_<mark style="color:green;">Please note: The User will be allowed to select the roles based on configuration at the application settings page. If the user is allowed to request for more than one role, in such scenario, all roles will be combined in the approval request for the approving authority to approve or deny. Similarly, based on the configuration, the user will be able to search and select only the roles allowed explicitly for the request. Example: business users shall not be allowed to request for Administrative type roles when raising the request.</mark>_ &#x20;

#### Approving an Application Request&#x20;

After a Cymmetri user has raised an approval request, the approver authority is selected by Cymmetri automatically. The approver is alerted by the system through a notification event in the user’s Notification tray. Cymmetri can also alert the approval user by way of an email sent to the user.  By clicking on the notification or the Application Requests short-link, the user is sent to the Inbox page.&#x20;

&#x20;The user can also view the notification request under the Request section on the user’s Dashboard. &#x20;

<figure><img src="../../.gitbook/assets/image (784).png" alt=""><figcaption></figcaption></figure>

Here, the user should click on Open menu under the Requests section to view all the pending application access requests.  On clicking one of the mail list items, the user can view the details of the application access request as shown above

&#x20;The approval user can now approve the request or mark their rejection for the access request. The approval user may provide comments for the action taken under the Comment box text area. &#x20;

<figure><img src="../../.gitbook/assets/image (785).png" alt=""><figcaption></figcaption></figure>

After clicking the Accept button, the user approves the application access request. Cymmetri shows the success message to the approval user. &#x20;

<figure><img src="../../.gitbook/assets/image (786).png" alt=""><figcaption></figcaption></figure>

Bulk Actions for Inbox Requests

This enhancement introduces the capability for approvers to execute bulk actions on multiple access requests directly from their inbox. By enabling approvers to select and manage several requests simultaneously, the system significantly reduces the manual effort and time required for processing. This feature is designed to improve operational efficiency, particularly during periods of high-volume reviews, thereby ensuring a more rapid turnaround for access provisioning. The user/admin can either Accept or Reject multiple requests simultaneously.

<figure><img src="../../.gitbook/assets/image1 (8).png" alt=""><figcaption></figcaption></figure>

#### Workflow Escalations and automatic request closure

Cymmetri allows flexible workflow configuration for managing closure of access requests in a time-bound manner. In case of an escalation scenario, the next in line reporting manager will be automatically escalated based on the turnaround time definition for the particular workflow step. The relevant users will be alerted through email notification of the escalation of such requests.&#x20;

If no escalation is defined, Cymmetri will automatically mark the request as rejected to end the request cycle. Cymmetri will alert the user of the automatic rejection via email notification.&#x20;

#### Viewing Application Request History&#x20;

Cymmetri users can view the history of processed requests by way of the Archive menu under the Requests section. The user can click on any one of the mail list items and view the details of the task.

<figure><img src="../../.gitbook/assets/image (787).png" alt=""><figcaption></figcaption></figure>

If an access request requires more than one level of approval, the same can be viewed one below the other with the following details -&#x20;

* Approver Name&#x20;
* Date and Time of approval&#x20;
* Approver comments (if any)&#x20;

#### Requesting Change in Application Access&#x20;

Cymmetri users can request a change in access role for applications assigned to them. The request process is managed from My Access > Application > Settings context menu. An approval request is generated once the user submits the role change request. &#x20;

The role change may not always require approval. In certain cases, the role change will be automatically applied as there is no approval workflow configured by the Cymmetri Administrator. &#x20;

## Claims&#x20;

Claims is the process of approving user access requests through any one approving authority in Cymmetri. In the event one approver is unavailable, it is likely that other approver(s) can stake a claim for the request and process the access request. &#x20;

The approvers are configured by the Cymmetri Administrator. The approver level can be defined as a single user, a reporting manager, or a group of users.&#x20;

A claim request can be accessed from the Dashboard or the Notification tray. &#x20;

<figure><img src="../../.gitbook/assets/image (792).png" alt=""><figcaption></figcaption></figure>

A click on the notification or claims short-link will land the user on the Claims section of the Inbox.&#x20;

<figure><img src="../../.gitbook/assets/image (793).png" alt=""><figcaption></figcaption></figure>

The user can click on any one of the mail list items under Claims section, and view the details of task. &#x20;

<figure><img src="../../.gitbook/assets/image (794).png" alt=""><figcaption></figcaption></figure>

Once the user clicks on the Claim button, the request moves from the Claims section to the Requests section. The claim user sees the success message "Task claimed successfully," and the user is automatically guided to the Open menu.  &#x20;

<figure><img src="../../.gitbook/assets/image (795).png" alt=""><figcaption></figcaption></figure>

The user can click on the list item and view the details for the access request. The approver can leave comments if needed and Accept to approve or Reject the request.  &#x20;

<figure><img src="../../.gitbook/assets/image (791).png" alt=""><figcaption></figcaption></figure>

Once approved successfully, the user will see the success notification.&#x20;

## My Requests&#x20;

The My Requests section lists all the application access requests raised by the logged-in user. Here, the user can view the status of the application access requests raised and review the access grant history.&#x20;

#### Open&#x20;

The Open menu lists all the requests yet to be approved for the user. &#x20;

<figure><img src="../../.gitbook/assets/image (789).png" alt=""><figcaption></figcaption></figure>

#### Closed&#x20;

The Closed menu lists all the requests that have been either approved or rejected for access.  By clicking on one of the mail list items, the user can view the history of the task. The details of the approve or reject action can be seen with the time and date of such an action, as well as the comments of the approver if any. &#x20;

<figure><img src="../../.gitbook/assets/image (788).png" alt=""><figcaption></figcaption></figure>
