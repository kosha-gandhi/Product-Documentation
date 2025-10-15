# User Settings

Cymmetri provides users with control over their individual account preferences, security settings, and personal information. Here are some common features and settings you can find on Cymmetri's account settings page:

Cymmetri users have the option to access the account settings page by clicking on the account dropdown located in the top right corner of the page and subsequently choosing the "Settings" option.

<figure><img src="../../.gitbook/assets/image (188).png" alt=""><figcaption></figcaption></figure>

#### My Profile

Users can view their profile on the My Profile section, where user can see their information such as

* Contact Info
* Basic Info
* Organization info
* Other Info

<figure><img src="../../.gitbook/assets/image (192).png" alt=""><figcaption></figcaption></figure>

#### Change Password

In the Change password section, users can reset their Cymmetri account password. They can do so by entering their current password,  new password, confirm new password fields.&#x20;

The users must ensure that the password they set must adhere to Cymmetri's password policy.&#x20;

<figure><img src="../../.gitbook/assets/image (193).png" alt=""><figcaption></figcaption></figure>

#### Secret Questions&#x20;

Within the Secret Questions section, users can review all the secret questions they have configured as part of multifactor authentication to log into Cymmetri. Additionally, users are provided with the option to reset these questions directly from this section.

<figure><img src="../../.gitbook/assets/image (557).png" alt=""><figcaption></figcaption></figure>

You can learn more about secret questions based authentication [here ](../../single-sign-on/multifactor-authentication-mfa/secret-questions.md)

#### Additional Verification (MFA)

The user from this section can view the additional factors of verification in this section.&#x20;

If multiple factors of authentication are available for that user to authenticate themselves in Cymmetri he/she can either

* Remove the factor&#x20;
* Setup the factor

<figure><img src="../../.gitbook/assets/image (559).png" alt=""><figcaption></figcaption></figure>

Note: SMS Authenticator cannot be removed by the user&#x20;

You can learn more about multifactor authentication [here](../../single-sign-on/multifactor-authentication-mfa/).

#### Trusted Devices

The trusted devices sections shows any values if adaptive mfa is applicable to the user and user logs in from a certain device. Based on the configuration done in adaptive mfa only after a particular number of successful logins from a device, the device becomes a trusted device. Unless and until you don't reach the specified number of successful login  attempts the device appears as below where you can see a <mark style="color:red;">red cross</mark> appearing in the Trusted column which indicates that the device mentioned is not yet a trusted device.

<figure><img src="../../.gitbook/assets/image (991).png" alt=""><figcaption></figcaption></figure>

Once the specified number of successful login attempts are reached the device becomes a trusted device and a green tick appear in the Trusted column as shown below. Once the device is trusted, any number of logins that the user does then from that device are not asked for a second level authentication if that is how it is configured.

<figure><img src="../../.gitbook/assets/image (992).png" alt=""><figcaption></figcaption></figure>

#### User Sessions&#x20;

In the User Sessions section, users have the capability to observe all currently active user sessions, displaying details such as the browser, operating system, login ID, IP address, and the timestamp of when the user session was initiated. Each session entry includes a delete button, providing users with the ability to revoke individual sessions.

Additionally, users can choose to revoke all of their active sessions simultaneously by selecting the "Revoke All Sessions" option.&#x20;

This feature enhances user control and security by allowing for efficient management of active sessions.

<figure><img src="../../.gitbook/assets/image (560).png" alt=""><figcaption></figcaption></figure>

#### Delegation to me&#x20;

In this section the user can view all the delegations that has been assigned to him/her with details such as: Delegated By, Start Date, End Date, Excluded applications and accept button to accept the delegation.

Delegation feature in Cymmetri is explained in detail [here](../../identity-hub/managing-users-and-groups/delegation/).

<figure><img src="../../.gitbook/assets/image (561).png" alt=""><figcaption></figcaption></figure>

#### My Delegations&#x20;

In the My Delegation section, the user can view the delegations they have assigned to other user.

You can learn more about Delegation [here](../../identity-hub/managing-users-and-groups/delegation/).

<figure><img src="../../.gitbook/assets/image (562).png" alt=""><figcaption></figcaption></figure>

