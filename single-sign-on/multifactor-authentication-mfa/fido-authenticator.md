# FIDO Authenticator

The FIDO (“Fast IDentity Online”) Authenticator is a hardware device or software solution designed to provide secure access to services and applications through robust, user-friendly authentication methods. FIDO Authenticators support multiple authentication technologies including biometrics (such as fingerprint recognition, facial recognition), security keys, and mobile devices.

### Key Features of FIDO Authenticator

* **Strong Authentication**: By using cryptographic techniques, FIDO Authenticator ensure a high level of security, making unauthorized access significantly more difficult.
* **Privacy-Focused**: Biometric data, when used, does not leave the device. This ensures that personal information is kept secure and private.
* **Ease of Use**: FIDO authentication simplifies the user experience by allowing a single gesture, like a fingerprint swipe or facial recognition, to quickly access services without remembering passwords.
* **Versatility**: These authenticators are designed to work across a wide range of devices and platforms, ensuring seamless integration into users’ digital lives.
* **Phishing Resistant**: Because authentication is tied to the user’s device and uses cryptographic keys, it is virtually impossible for attackers to replicate or steal credentials through phishing attacks.

### Configuration

For configuring FIDO Authenticator in Cymmetri, select the FIDO Authenticator toggle button and click confirm to setup FIDO Authenticator as an MFA option

<figure><img src="../../.gitbook/assets/image (718).png" alt=""><figcaption></figcaption></figure>

Next move to configure the rules for Multi-factor authentication policy for login

<figure><img src="../../.gitbook/assets/image (717).png" alt=""><figcaption></figcaption></figure>

You may either click on the pencil icon to start editing the rule, or create a new rule as shown below:

<figure><img src="../../.gitbook/assets/image (716).png" alt=""><figcaption></figcaption></figure>

Once you have either created a new rule or edited an existing one, change the dropdown of the FIDO Authenticator factor to indicate that it is mandatory (required).

<figure><img src="../../.gitbook/assets/image (715).png" alt=""><figcaption></figcaption></figure>

The options available for each factor are:

**Required**: This setting means that the corresponding factor is required to be enabled for each user, and every user must set up this factor in their next login.

**Optional**: This setting means that the corresponding factor is not required to be enabled for each user, and they may configure this option from their "My Workspace". Once the user configures it, they may use it for the purpose of second level of authentication during authentication.\
\
**Disabled**: This settings means that the corresponding factor is not required or enabled for each user, and the user may not configure or use it for authentication into the Cymmetri platform.

An administrator can further customize to whom the rule would be applicable by selecting user(s) or group of users in the "_Assigned to_" Tab, If the rule is to be applied to all the users then the "_All Users_" option need to be selected

<figure><img src="../../.gitbook/assets/image (714).png" alt=""><figcaption></figcaption></figure>

Once the changes are saved this is how the rule appears:

<figure><img src="../../.gitbook/assets/image (713).png" alt=""><figcaption></figcaption></figure>

All subsequent logins of any user on the Cymmetri Identity platform will now require the use of the  FIDO Authenticator mechanism.

<figure><img src="../../.gitbook/assets/image (712).png" alt=""><figcaption></figcaption></figure>

The user needs to setup the Cymmetri Authenticator for receiving the push notification on the device, for which the user needs to download the Cymmetri Verifier app. The links below can be used to download the Cymmetri Verifier App on Android or IOS:

IOS- [https://apps.apple.com/in/app/cymmetri-verify/id6455987489](https://apps.apple.com/in/app/cymmetri-verify/id6455987489)

Android - [https://play.google.com/store/apps/details?id=com.cymmetri.verify](https://play.google.com/store/apps/details?id=com.cymmetri.verify)

Once downloaded we need to scan the QR Code in the Cymmetri Verifier App to register the device

<figure><img src="../../.gitbook/assets/image (711).png" alt=""><figcaption></figcaption></figure>

Once the device is registered successfully a notification is show on the dashboard&#x20;

<figure><img src="../../.gitbook/assets/image (710).png" alt=""><figcaption></figcaption></figure>

Now when the user selects FIDO Authenticator as an MFA mechanism and consent notification is sent to the mobile device (The consent notification appears as shown below) and the user needs to accept the consent in the stipulated time to be allowed to login also after the user accepts the consent the user needs to prove their identity by providing biometrics (such as fingerprint recognition, facial recognition).

<div><figure><img src="../../.gitbook/assets/image (707).png" alt="" width="135"><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (709).png" alt="" width="288"><figcaption></figcaption></figure></div>

Once successfully verified the user is redirected to the Dashboard

<figure><img src="../../.gitbook/assets/image (706).png" alt=""><figcaption></figcaption></figure>

