# Cymmetri Authenticator

The Cymmetri Authenticator is a robust multi-factor authentication (MFA) mechanism. This mechanism enhances digital security by adding an additional layer of authentication to verify user identity, using a time based OTP (TOTP)

The Cymmetri Authenticator uses the Cymmetri Verifier App that generates time-based one-time passwords (TOTPs) that expire after a short time window. Users must enter these constantly changing codes along with their regular passwords to gain access to their accounts, ensuring that even if a malicious actor obtains their password, access remains highly restricted.

The Cymmetri Authenticator App is user-friendly and easy to set up, often by scanning QR codes provided by the service requiring authentication. It's a valuable tool for businesses and individuals looking to protect their sensitive data effectively.&#x20;

### Configuration

For configuring the Cymmetri Authenticator, select the Cymmetri Authenticator (Time based OTP) toggle button and click confirm to setup Cymmetri Authenticator as an MFA option

<figure><img src="../../.gitbook/assets/image (125).png" alt=""><figcaption></figcaption></figure>

Next we move to configure the rules for Multi-factor authentication policy for login

<figure><img src="../../.gitbook/assets/image (702).png" alt=""><figcaption></figcaption></figure>

Click on the pencil icon to start editing the rule.

To enable this rule click on the pencil icon in the upper box to toggle on this rule.

<figure><img src="../../.gitbook/assets/image (261).png" alt=""><figcaption></figcaption></figure>

Change the dropdown of the Cymmetri Authenticator factor to indicate that it is mandatory (required).

<figure><img src="../../.gitbook/assets/image (260).png" alt=""><figcaption></figcaption></figure>

The options available for each factor are:

**Required**: This setting means that the corresponding factor is required to be enabled for each user, and every user must set up this factor in their next login.

**Optional**: This setting means that the corresponding factor is not required to be enabled for each user, and they may configure this option from their "My Workspace". Once the user configures it, they may use it for the purpose of second level of authentication during authentication.\
\
**Disabled**: This settings means that the corresponding factor is not required or enabled for each user, and the user may not configure or use it for authentication into the Cymmetri platform.

An administrator can further customize to whom the rule would be applicable by selecting user(s) or group of users in the "_Assigned to_" Tab, If the rule is to be applied to all the users then the "_All Users_" option need to be selected

<figure><img src="../../.gitbook/assets/image (407).png" alt=""><figcaption></figcaption></figure>

All subsequent logins of any user on the Cymmetri platform will now require the use of the  Cymmetri Authenticator Code.

<figure><img src="../../.gitbook/assets/image (408).png" alt=""><figcaption></figcaption></figure>

The user needs to setup the Cymmetri Authenticator, for which the user needs to download the Cymmetri Verifier app. The links below can be used to download the Cymmetri Verifier App on Android or IOS:

IOS- [https://apps.apple.com/in/app/cymmetri-verify/id6455987489](https://apps.apple.com/in/app/cymmetri-verify/id6455987489)

Android - [https://play.google.com/store/apps/details?id=com.cymmetri.verify](https://play.google.com/store/apps/details?id=com.cymmetri.verify)

Once downloaded we need to scan the QR Code as shown below in the Cymmetri Verifier App and obtain a 6 digit code which needs to be entered in the space provided below and verify the user login.

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003457235/original/XFsfgN2RTmvBTtuRwo8QCggMfXDZKR4Mvg.png?1649369359)

Once successfully verified the user is redirected to the Dashboard

<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003393288/original/b6nAcDeUFiw_EoJjRfx2O-F19m0X3YCRVw.png?1649310458" alt=""><figcaption></figcaption></figure>

Cymmetri also allow you to customize the Cymmetri Authenticator parameters using the Configuration section. Here you may configure the values as shown below:

**OTP Type:** Select the OTP Type to be implemented.Time Based is the default value here.

**OTP Hash Algorithm:** Select the appropriate cryptographic algorithm to generate the OTP. Default option is HmacSHA1.&#x20;

**Number of Digits:** The length of the generated OTPs, which can be 6-9 numbers. The default is 6.&#x20;

**OTP Token Period:** This number determines how long a one-time password is active before the next one-time password generates. The default is 30 seconds.&#x20;

**Look Ahead Window:** The Look Ahead Window considers any possible synchronization delay between the server and the client that generates the one-time password. Default value is 2. The look ahead window can also be set to 0 which means that only the current TOTP can be used.

_<mark style="color:blue;">Note: Whenever the lookahead window value is changed, existing users need to remove there existing configuration and re-register for the changed lookaheadwindow value to be applicable</mark>_



**Supported Applications:** Two-Factor Authentication apps that can be used by users to secure their Cymmetri IAM accounts.

<figure><img src="../../.gitbook/assets/image (433).png" alt=""><figcaption></figcaption></figure>
