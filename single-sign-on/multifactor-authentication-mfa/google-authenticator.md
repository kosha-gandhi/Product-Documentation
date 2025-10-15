# Google Authenticator

Google Authenticator is a widely used two-factor authentication app developed by Google. It generates time-based one-time passcodes (TOTPs) on users' mobile devices, providing an additional layer of security beyond passwords. Users typically scan QR codes presented by online services to set up two-factor authentication.

### Configuration

For configuring the Google Authenticator, select the Google Authenticator toggle button and click confirm to setup Google Authenticator as an MFA option

<figure><img src="../../.gitbook/assets/image (502).png" alt=""><figcaption></figcaption></figure>

Next we move to configure the rules for Multi-factor authentication policy for login

<figure><img src="../../.gitbook/assets/image (503).png" alt=""><figcaption></figcaption></figure>

You may either click on the pencil icon to start editing the rule, or create a new rule

Once you have either created a new rule or edited an existing one, change the dropdown of the Google Authenticator factor to indicate that it is mandatory (required).

<figure><img src="../../.gitbook/assets/image (504).png" alt=""><figcaption></figcaption></figure>

The options available for each factor are:

**Required**: This setting means that the corresponding factor is required to be enabled for each user, and every user must set up this factor in their next login.

**Optional**: This setting means that the corresponding factor is not required to be enabled for each user, and they may configure this option from their "My Workspace". Once the user configures it, they may use it for the purpose of second level of authentication during authentication.\
\
**Disabled**: This settings means that the corresponding factor is not required or enabled for each user, and the user may not configure or use it for authentication into the Cymmetri platform.

An administrator can further customize to whom the rule would be applicable by selecting user(s) or group of users in the "_Assigned to_" Tab, If the rule is to be applied to all the users then the "_All Users_" option need to be selected

<figure><img src="../../.gitbook/assets/image (506).png" alt=""><figcaption></figcaption></figure>

Once the changes are saved this is how the rule appears:

<figure><img src="../../.gitbook/assets/image (507).png" alt=""><figcaption></figcaption></figure>

All subsequent logins of any user on the Cymmetri platform will now require the use of the  Google Authenticator Code.

<figure><img src="../../.gitbook/assets/image (508).png" alt=""><figcaption></figcaption></figure>

The user needs to setup the Google Authenticator, for which the user needs to download the Google Authenticator App. The links below can be used to download the Google Authenticator App on Android or IOS:

Android: [https://play.google.com/store/apps/details?id=com.google.android.apps.authenticator2\&pcampaignid=web\_share](https://play.google.com/store/apps/details?id=com.google.android.apps.authenticator2\&pcampaignid=web_share)

IOS: [https://apps.apple.com/gb/app/google-authenticator/id388497605](https://apps.apple.com/gb/app/google-authenticator/id388497605)

Once downloaded we need to scan the QR Code as shown below in the Google Authenticator App and obtain a 6 digit code which needs to be entered in the space provided below and verify the user login.

<figure><img src="../../.gitbook/assets/image (509).png" alt=""><figcaption></figcaption></figure>

Once successfully verified the user is redirected to the Dashboard

<figure><img src="../../.gitbook/assets/image (510).png" alt=""><figcaption></figcaption></figure>

Cymmetri also allow you to customize the Cymmetri Authenticator parameters using the Configuration section. Here you may configure the values as shown below:

**OTP Type:** Select the OTP Type to be implemented.Time Based is the default value here.

**OTP Hash Algorithm:** Select the appropriate cryptographic algorithm to generate the OTP. Default option is HmacSHA1.&#x20;

**Number of Digits:** The length of the generated OTPs, which can be 6-9 numbers. The default is 6.&#x20;

**OTP Token Period:** This number determines how long a one-time password is active before the next one-time password generates. The default is 30 seconds.&#x20;

**Look Ahead Window:** The Look Ahead Window considers any possible synchronization delay between the server and the client that generates the one-time password. Default value is 2. The look ahead window can also be set to 0 which means that only the current TOTP can be used.

_<mark style="color:blue;">Note: Whenever the lookahead window value is changed, existing users need to remove there existing configuration and re-register for the changed lookaheadwindow value to be applicable</mark>_

**Supported Applications:** Two-Factor Authentication apps that can be used by users to secure their Cymmetri IAM accounts.

<figure><img src="../../.gitbook/assets/image (511).png" alt=""><figcaption></figcaption></figure>
