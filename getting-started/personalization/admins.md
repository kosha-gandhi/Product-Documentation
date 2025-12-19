# Admins

Cymmetri platform has six different admin roles with various levels of access to the various menus and resources on the administration portal of Cymmetri.

In addition to these six admin roles, Cymmetri also supports three different privileged user roles that grant varying levels of access (read, write, report) to privileged users within Cymmetri.

<figure><img src="../../.gitbook/assets/image (457).png" alt=""><figcaption></figcaption></figure>

### Administrators

The various admin roles on the Cymmetri Identity Platform may be described as follows:

#### Organization Administrator&#x20;

This is the so-called 'super admin' administrator role in the Cymmetri platform. Administrators with this role have the authorization to modify any settings or make changes to the tenant.

#### Domain Administrator&#x20;

This is a slightly less privileged administrator. Most tenant-wide system settings, such as the configuration of SMS and email providers (when configured by the tenant), are restricted for domain administrators. All other configurations can be viewed and edited by administrators with the Domain Administrator role.

#### Application Administrator&#x20;

An administrator with the role of Application Administrator has access to Identity Hub configurations, including Application, User, and Group configurations. The Application Administrator can map users and groups to applications and can edit all configurations related to Application Management.

#### Report Administrator&#x20;

An administrator with the role of Report Administrator has access to the Reports menu, which includes the ability to view, modify, and add new reports.

#### Help Desk Administrator&#x20;

The Helpdesk administrator has access to a very limited set of administrative functionalities, such as resetting the password of the end-user, removing configured Multifactor authentication options, and other such common use cases.

#### Read Only Administrator&#x20;

All administrative users have editing access to the various administrative sections of the Cymmetri platform. However, administrators with the "Read Only Administrator" role do not have editing access to any of the settings or configurations; they only have "Read Only" access to the administrative section.

#### PAM Write Access

PAM Write Access in Cymmetri grants users the privilege to connect to servers via RDP or SSH and perform write or modification actions on those servers. Users with PAM Write Access have the ability to make changes, update configurations, and perform tasks that involve altering data or settings on the connected servers. This access level is typically assigned to administrators and IT personnel responsible for making configuration changes or updates on various servers within the Cymmetri environment.

#### PAM Read Access

PAM Read Access provides users with the ability to connect to servers using RDP or SSH and view the content and configurations on those servers. However, users with PAM Read Access do not have the authority to make modifications or changes to the server settings or data. This level of access is suitable for individuals who need to monitor server activities, check logs, or retrieve information from servers without the need to alter any server configurations.

#### PAM Report Access

PAM Report Access is designed for users who require access to PAM-related reports without the need to connect to servers via RDP or SSH directly. Users with PAM Report Access can generate and access reports that provide insights into server activities, access logs, or other relevant data within Cymmetri. Such users can also configure schedulers to send timely reports to various other users. This level of access is beneficial for auditors, compliance teams, or individuals focused on analyzing server-related information for reporting and auditing purposes.

### Adding a New Admin

Follow the steps mentioned below to promote a user as an admin in the Cymmetri platform.

Click on the Configuration menu on the right-hand side&#x20;

<figure><img src="../../.gitbook/assets/image (458).png" alt="" width="184"><figcaption></figcaption></figure>

Now, click on the Admins sub-menu within the Configuration menu

<figure><img src="../../.gitbook/assets/image (459).png" alt=""><figcaption></figcaption></figure>

Click on the "**+Add New**" button to add a new administrator<br>

<figure><img src="../../.gitbook/assets/image (396).png" alt=""><figcaption></figcaption></figure>

To assign an administrator role to a user, search for the user and then click the 'Assign' button.

<figure><img src="../../.gitbook/assets/image (397).png" alt=""><figcaption></figcaption></figure>

Select the chosen administration role and click on Save

<figure><img src="../../.gitbook/assets/image (398).png" alt=""><figcaption></figcaption></figure>

The administrator has been assigned the role of “Report Administrator”.

#### All Admins&#x20;

All admins is a section where various Cymmetri admins are displayed to the admin user&#x20;

<figure><img src="../../.gitbook/assets/image (460).png" alt=""><figcaption></figcaption></figure>
