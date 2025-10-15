# FIDO Based

FIDO (Fast Identity Online) is an open standard for passwordless authentication that aims to reduce reliance on passwords and enhance online security. FIDO-based passwordless mechanisms use public-key cryptography to authenticate users without the need for traditional passwords. One of the key components of FIDO is the use of a hardware security key or biometric authentication.

Here's a brief overview of how FIDO-based passwordless mechanisms work:

1. **Registration:**
   * During the registration process, the user's device generates a public-private key pair.
   * The public key is stored on the server, while the private key remains on the user's device. The private key is typically stored in a secure element, such as a hardware security key or the device's Trusted Platform Module (TPM).
2. **Authentication:**
   * When a user attempts to log in, the server sends a challenge to the user's device.
   * The device uses the private key to sign the challenge and sends the signed response back to the server.
   * The server verifies the signature using the stored public key. If the verification is successful, the user is authenticated.
3. **FIDO Protocols:**
   * FIDO supports two main protocols: FIDO U2F (Universal 2nd Factor) and FIDO2.
   * Cymmetri supports the FIDO2 protocol for implemeting the passwordless mechanism
   * FIDO2 includes WebAuthn (for web applications) for communication between the client (user's device) and the authenticator (e.g., hardware security key).
4. **Passwordless Options:**
   * FIDO-based passwordless authentication can be achieved through various methods, including the use of hardware security keys, biometrics (such as fingerprint or facial recognition), or a combination of both.





<figure><img src="../../.gitbook/assets/image (200).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (199).png" alt=""><figcaption></figcaption></figure>

