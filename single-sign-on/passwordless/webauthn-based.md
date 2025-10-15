# WebAuthn Based

WebAuthn provides a highly secure and user-friendly method for users to log into their specific instances.

Here's a breakdown of how Cymmetri facilitates this:

1. **Eliminating Passwords for Login:**
   * Instead of relying on traditional passwords to access, users would register one or more WebAuthn authenticators (e.g., their smartphone with biometrics, a hardware security key, or built-in laptop authenticators like Windows Hello/Touch ID).
   * This registration process would be facilitated through Cymmetri's user portal, securely linking the public key of the authenticator to the user's identity within Cymmetri.
2. **Simplified and Secure Tenant Access:**
   * When a user attempts to log in (e.g., `mycompany.cymmetri.com/tenantA`), Cymmetri's login page would initiate a WebAuthn challenge.
   * The user's browser, in conjunction with Cymmetri's authentication flow, would prompt them to verify their identity using their registered device.
   * This typically involves a simple, explicit user action on their trusted device:
     * **Biometric Scan:** A fingerprint scan or face recognition on their smartphone or laptop.
     * **PIN/Pattern:** Entering a PIN or pattern configured on their device for authentication.
     * **Physical Touch:** Tapping a button on a hardware security key.
   * This "explicit consent and user approval" mechanism ensures that only the legitimate user with their registered device can gain access to their tenant.

Here is how the admin can set up this functionality:

1. Passwordless > Configuration > WebAuthn Based

<figure><img src="../../.gitbook/assets/image (1012).png" alt=""><figcaption></figcaption></figure>

2. The user can enable this from the Settings

<figure><img src="../../.gitbook/assets/image (1013).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (1014).png" alt=""><figcaption></figcaption></figure>

Select your desired way of login. Once that is completed, this screen will be visible.&#x20;

<figure><img src="../../.gitbook/assets/image (1015).png" alt=""><figcaption></figcaption></figure>

On the user login page, this is how the passwordless way.

<figure><img src="../../.gitbook/assets/image (1019).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (1020).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (1021).png" alt=""><figcaption></figcaption></figure>

Once you accept the request, the user will enter their system.&#x20;
