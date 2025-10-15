# SMS Authenticator

SMS Authenticator involves sending a unique verification code to the user's mobile device via SMS and/ or to the user's email. The user then enters this code along with their password to complete the login process.

### Configuration

For configuring the SMS Authenticator, select the SMS Authenticator toggle button and click confirm to setup SMS Authenticator as an MFA option

<figure><img src="../../.gitbook/assets/image (212).png" alt=""><figcaption></figcaption></figure>

Next we move to configure the rules for Multi-factor authentication policy for login

You may either click on the pencil icon to start editing the rule, or create a new rule

<figure><img src="../../.gitbook/assets/image (213).png" alt=""><figcaption></figcaption></figure>

Once you have either created a new rule or edited an existing one, change the dropdown of the SMS Authenticator factor to indicate that it is mandatory (required).

<figure><img src="../../.gitbook/assets/image (214).png" alt=""><figcaption></figcaption></figure>

The options available for each factor are:

**Required**: This setting means that the corresponding factor is required to be enabled for each user, and every user must set up this factor in their next login.

**Optional**: This setting means that the corresponding factor is not required to be enabled for each user, and they may configure this option from their "My Workspace". Once the user configures it, they may use it for the purpose of second level of authentication during authentication.\
\
**Disabled**: This settings means that the corresponding factor is not required or enabled for each user, and the user may not configure or use it for authentication into the Cymmetri platform.

An administrator can further customize to whom the rule would be applicable by selecting user(s) or group of users in the "_Assigned to_" Tab, If the rule is to be applied to all the users then the "_All Users_" option need to be selected

<figure><img src="../../.gitbook/assets/image (215).png" alt=""><figcaption></figcaption></figure>

Once the changes are saved this is how the rule appears:

<figure><img src="../../.gitbook/assets/image (216).png" alt=""><figcaption></figcaption></figure>

All subsequent logins of any user on the Cymmetri platform will now require the use of sms received on the mobile device as an SMS or email.

<figure><img src="../../.gitbook/assets/image (217).png" alt=""><figcaption></figcaption></figure>

Once successfully verified the user is redirected to the Dashboard

<figure><img src="../../.gitbook/assets/image (218).png" alt=""><figcaption></figcaption></figure>

Cymmetri also allow you to customize the SMS Authenticator parameters using the Configuration section. Here you may configure the values as shown below:

**Number of Digits:** The length of the generated OTPs, which can be 4-6 numbers. Default is 6.&#x20;

**OTP Expiry (Minutes):** This number determines how long a one-time password is active before it expires and a new OTP needs to be generated. Default is 10 minutes.

**OTP Resent Time:** The number of OTP resend requests allowed by the server in the case of SMS lost in transmission. Default is 2.

**OTP on Email:** when enabled OTP is sent on email.

**OTP on SMS:** when enabled OTP is sent as an SMS on user's mobile device

<figure><img src="../../.gitbook/assets/image (219).png" alt=""><figcaption></figcaption></figure>
