# Push Authenticator

Push Authenticator is a modern and highly convenient multi-factor authentication (MFA) mechanism of Cymmetri's Multi-factor Authentication mechanisms designed to bolster security while offering a user-friendly experience. This authentication method simplifies the process of verifying one's identity, reducing the reliance on traditional methods like SMS codes or hardware tokens.

With Push Authenticator, users receive authentication requests directly on their registered mobile devices. A push notification is sent to the user's device in the Cymmetri Authenticator App, prompting them to approve or deny the login attempt. This approval process occurs with a simple tap.

The advantages of Push Authenticator are twofold. First, it enhances security by reducing the risk of intercepted codes or phishing attacks. Second, it streamlines the user experience, making MFA more accessible and less intrusive.

### Configuration

For configuring the Push Authenticator, select the Push Notification toggle button and click confirm to setup Push Authenticator as an MFA option

<figure><img src="../../.gitbook/assets/image (699).png" alt=""><figcaption></figcaption></figure>

And click confirm to setup Push Authenticator as an MFA option

<figure><img src="../../.gitbook/assets/image (700).png" alt=""><figcaption></figcaption></figure>

Next we move to configure the rules for Multi-factor authentication policy for login

<figure><img src="../../.gitbook/assets/image (701).png" alt=""><figcaption></figcaption></figure>

Click on the pencil icon to start editing the rule.Optionally you may also add a new rule by clicking on the "+ Add New" button.&#x20;

For adding a New Rule enter Name of the Rule and Description also Enable the rule; you may optionally select whether you want to enable Adaptive MFA and the click on the Save button to add the rule<br>

<figure><img src="../../.gitbook/assets/image (257).png" alt=""><figcaption></figcaption></figure>

Once added you need to configure the rule to select the Push Authenticator mechanism as **Required** and enable it.&#x20;

<figure><img src="../../.gitbook/assets/image (258).png" alt=""><figcaption></figcaption></figure>

The other options that can be selected are as explained below:

**Required**: This setting means that the corresponding factor is required to be enabled for each user, and every user must set up this factor in their next login.

**Optional**: This setting means that the corresponding factor is not required to be enabled for each user, and they may configure this option from their "My Workspace". Once the user configures it, they may use it for the purpose of second level of authentication during authentication.\
\
**Disabled**: This settings means that the corresponding factor is not required or enabled for each user, and the user may not configure or use it for authentication into the Cymmetri platform.



An administrator can further customize to whom the rule would be applicable by selecting user(s) or group of users in the "_Assigned to_" Tab, If the rule is to be applied to all the users then the "_All Users_" option need to be selected

<figure><img src="../../.gitbook/assets/image (407).png" alt=""><figcaption></figcaption></figure>

All subsequent logins of any user on the Cymmetri Identity platform will now require the use of the  Push Authenticator mechanism.

<figure><img src="../../.gitbook/assets/image (412).png" alt=""><figcaption></figcaption></figure>

The user needs to setup the Cymmetri Authenticator for receiving the push notification on the device, for which the user needs to download the Cymmetri Verifier app. The links below can be used to download the Cymmetri Verifier App on Android or IOS:

IOS- [https://apps.apple.com/in/app/cymmetri-verify/id6455987489](https://apps.apple.com/in/app/cymmetri-verify/id6455987489)

Android - [https://play.google.com/store/apps/details?id=com.cymmetri.verify](https://play.google.com/store/apps/details?id=com.cymmetri.verify)

Once downloaded we need to scan the QR Code in the Cymmetri Verifier App to register the device

<figure><img src="../../.gitbook/assets/image (413).png" alt=""><figcaption></figcaption></figure>

Once the device is registered successfully a notification is show on the dashboard&#x20;

<figure><img src="../../.gitbook/assets/image (414).png" alt=""><figcaption></figcaption></figure>

Now when the user selects Push Authenticator as an MFA mechanism and consent notification is sent to the mobile device and the user needs to accept the consent in the stipulated time to be allowed to login.

<figure><img src="../../.gitbook/assets/image (415).png" alt=""><figcaption></figcaption></figure>

A notification like as shown below appears on the mobile device where the user needs to click on Yes button to allow login

<figure><img src="../../.gitbook/assets/image (416).png" alt="" width="270"><figcaption></figcaption></figure>

Once successfully verified the user is redirected to the Dashboard

<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003393288/original/b6nAcDeUFiw_EoJjRfx2O-F19m0X3YCRVw.png?1649310458" alt=""><figcaption></figcaption></figure>
