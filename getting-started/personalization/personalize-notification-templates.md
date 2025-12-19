# Personalize Notification Templates

Notifications are triggered from the Cymmetri platform for various actions occurring on the platform either through direct action by the end-user or by the virtue of some backend action (such as running of a scheduler for a campaign). Cymmetri platform ships with default notification templates listed below-

1. **Mandatory Notifications**

* Sign-up / Registration
* OTP Notification
* Access Code Manager Notification
* Access Code User Notification

<figure><img src="../../.gitbook/assets/image (917).png" alt=""><figcaption></figcaption></figure>

2. **Optional Notifications**

* Workflow Notification
* Reviewer Notification
* Application Access Approval Request
* Application Assignment
* Delegation Assignee Notification
* User Activation&#x20;
* Application Scheduled Deprovisioning
* Delegation User Notification
* Application Access Approval Request Denied by Approver
* Application Access Approval Request Granted
* User Notification&#x20;
* Login Failed
* Password Expiry Notification&#x20;
* Review Assignment Notification
* Self Approval Notification&#x20;
* Login Adaptive Failed Notification&#x20;
* MFA Failed Notification&#x20;
* User Threshold&#x20;
* User attribute update / Profile update
* Pending Access Certification Notification
* Ad-Hoc Certification Notification
* User Risk score changes&#x20;
* Requestee Notification
* Requestor Notification

<figure><img src="../../.gitbook/assets/image (913).png" alt=""><figcaption></figcaption></figure>

_<mark style="color:green;">Please note: The above notifications are available out of the box. The system also allows custom notifications to be triggered for specific events using the Cymmetri Webhooks. The custom action trigger can call an existing Cymmetri notification template or a custom template can be included in the webhook code.</mark>_&#x20;

The default templates may be modified by the administrator using the following process:

1.  Access the notification templates menu by clicking on the configuration menu on the left-hand side menu bar and then clicking on the Notification templates pop-up menu.

    <figure><img src="../../.gitbook/assets/image (403).png" alt=""><figcaption></figcaption></figure>
2. Click on the eye icon to preview the corresponding template

<figure><img src="../../.gitbook/assets/image (799).png" alt=""><figcaption></figcaption></figure>

3. Values in <> anchor tags and ${} reflect macros.
4.  Click on the pencil icon shown above the image to edit the template.<br>

    <figure><img src="../../.gitbook/assets/image (798).png" alt=""><figcaption></figcaption></figure>
5.  We may treat this template as an email and edit the subject of the email.

    By default, the email notification will be sent to the corresponding affected end-user, but selecting the toggle option for “Send notification to Reporting Manager” will also copy the mail to the Reporting Manager of the affected end-user, allowing for offline follow-up for the notification.<br>

    <figure><img src="../../.gitbook/assets/image (800).png" alt=""><figcaption></figcaption></figure>
6. The administrator may edit the HTML using the provided HTML editor to add/change any template button/text/background. The macros required for the particular template are already provided in the sample default notification template.
7. Click on the **Save** button to save the notification template.
