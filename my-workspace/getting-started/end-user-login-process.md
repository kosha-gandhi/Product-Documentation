# End User Login Process

The End User Login Process commences when a user accesses their designated tenant instance login page, which typically conforms to the structure: <mark style="color:blue;">https://\<company-name>.cymmetri.io</mark>

<figure><img src="../../.gitbook/assets/image (71).png" alt=""><figcaption></figcaption></figure>

Once, on the Cymmetri Login page, the user needs to enter their username, users receive their login credentials on their corporate email as shown below:

<figure><img src="../../.gitbook/assets/image (72).png" alt=""><figcaption></figcaption></figure>

If the administrator has enabled password-less login option, then the user sees the <mark style="color:blue;">Login without Password</mark> button, else the user sees only the <mark style="color:blue;">Login</mark> button.

<div data-full-width="true"><figure><img src="../../.gitbook/assets/image (350).png" alt=""><figcaption></figcaption></figure></div>

The user has the flexibility to select either a **password-based authentication** or a **passwordless authentication** mechanism during the login process.

### Password-based Authentication:

The steps below indicate the password-based authentication mechanism:  &#x20;

Once the username is entered and the user clicks on Next, the user then needs to enter the password received on their email, and click on the Login button.

<figure><img src="../../.gitbook/assets/image (73).png" alt=""><figcaption></figcaption></figure>

Depending on whether the administrator has enabled the multi-factor authentication options for the organization, and depending on the factors that the user has registered , the user is shown the various multi-factor authentication options.

<figure><img src="../../.gitbook/assets/image (349).png" alt=""><figcaption></figcaption></figure>

<mark style="color:blue;">**Option 1**</mark> - Choosing Cymmetri Authenticator will require the user to enter their Time-based OTP as it appears on your Cymmetri Authenticator mobile application. The user needs to enter the TOTP and click on Verify to continue.

<figure><img src="../../.gitbook/assets/image (848).png" alt=""><figcaption></figcaption></figure>

<mark style="color:blue;">**Option 2**</mark> - Choosing Push Authenticator will send a push notification to the user's mobile phone and the user may click on the accept button to complete the login process.

<figure><img src="../../.gitbook/assets/image (363).png" alt=""><figcaption></figcaption></figure>

<mark style="color:blue;">**Option 3**</mark> - Choosing Google Authenticator will require the user to enter their Time-based OTP as it appears on their Google Authenticator mobile application. The user needs to enter the TOTP and click on Verify to continue.

<figure><img src="../../.gitbook/assets/image (849).png" alt="" width="444"><figcaption></figcaption></figure>

<mark style="color:blue;">**Option 4**</mark> - Choosing SMS Authenticator will send an OTP to the user's registered mobile number and the user is expected to enter this OTP and Click on Verify to continue.

<figure><img src="../../.gitbook/assets/image (850).png" alt="" width="403"><figcaption></figcaption></figure>

<mark style="color:blue;">**Option 5**</mark> - Choosing Secret Questions Authenticator will ask the user to answer a certain number of questions as selected by the user and once answered the user may Click on Next to continue.

<figure><img src="../../.gitbook/assets/image (359).png" alt=""><figcaption></figcaption></figure>

Regardless of the flow followed and the multi-factor authentication option chosen, the user will end up on the dashboard page below upon successful login.

<figure><img src="../../.gitbook/assets/image (360).png" alt=""><figcaption></figcaption></figure>

### Passwordless Authentication:

The steps below indicate the passwordless authentication mechanism:  &#x20;

1. To begin the Passwordless Login flow the user needs to click on the "Login without Password" button, this will trigger the password-less login flow, will show the various registered passwordless login options.

<figure><img src="../../.gitbook/assets/image (356).png" alt=""><figcaption></figcaption></figure>

<mark style="color:blue;">**Option 1**</mark> - Choosing TOTP Based Passwordless Login mechanism will require the user to enter their Time-based OTP as it appears on your Cymmetri Authenticator mobile application. The user needs to enter the TOTP and click on Verify to continue.

<figure><img src="../../.gitbook/assets/image (361).png" alt=""><figcaption></figcaption></figure>

<mark style="color:blue;">**Option 2**</mark> - Choosing OTP Based PasswordlessLogin mechanism will send an OTP to the user's registered mobile number and the user is expected to enter this OTP and Click on Verify to continue.

<figure><img src="../../.gitbook/assets/image (346).png" alt=""><figcaption></figcaption></figure>

<mark style="color:blue;">**Option 3**</mark> - Choosing the Consent Based Passwordless Login mechanism will send a push notification to the user's mobile phone and the user may click on the accept button to complete the login process.

<figure><img src="../../.gitbook/assets/image (363).png" alt=""><figcaption></figcaption></figure>

Regardless of the passwordless mechanism chosen to login , the user will end up on the dashboard page below upon successful login.

<figure><img src="../../.gitbook/assets/image (74).png" alt=""><figcaption></figcaption></figure>
