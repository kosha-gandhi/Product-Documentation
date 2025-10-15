# Secret Questions

Secret questions are a form of knowledge-based authentication where users set up personalized questions and provide answers during the account setup. These questions might serve as an additional layer of identity verification. Users are prompted to answer these questions during login or account recovery processes, supplementing other authentication methods.

### Enabling Secret Questions

For configuring the Secret Questions Authenticator, select the Secret Questions Authenticator toggle button and click confirm to setup Secret Questions Authenticator as an MFA option

<figure><img src="../../.gitbook/assets/image (704).png" alt=""><figcaption></figcaption></figure>

## Rules

Next we move to configure the rules for Multi-factor authentication policy for login

<figure><img src="../../.gitbook/assets/image (703).png" alt=""><figcaption></figcaption></figure>

You may either click on the pencil icon to start editing the rule, or create a new rule

<figure><img src="../../.gitbook/assets/image (705).png" alt=""><figcaption></figcaption></figure>

Once you have either created a new rule or edited an existing one, change the dropdown of the Secret Questions Authenticator factor to indicate that it is mandatory (required).

<figure><img src="../../.gitbook/assets/image (516).png" alt=""><figcaption></figcaption></figure>

The options available for each factor are:

**Required**: This setting means that the corresponding factor is required to be enabled for each user, and every user must set up this factor in their next login.

**Optional**: This setting means that the corresponding factor is not required to be enabled for each user, and they may configure this option from their "My Workspace". Once the user configures it, they may use it for the purpose of second level of authentication during authentication.\
\
**Disabled**: This settings means that the corresponding factor is not required or enabled for each user, and the user may not configure or use it for authentication into the Cymmetri platform.

An administrator can further customize to whom the rule would be applicable by selecting user(s) or group of users in the "_Assigned to_" Tab, If the rule is to be applied to all the users then the "_All Users_" option need to be selected

<figure><img src="../../.gitbook/assets/image (517).png" alt=""><figcaption></figcaption></figure>

Once the changes are saved this is how the rule appears:

<figure><img src="../../.gitbook/assets/image (518).png" alt=""><figcaption></figcaption></figure>

## Login with Secret Questions as MFA

All subsequent logins of any user on the Cymmetri platform will now require the use of the Secret Questions Authenticator and answer the configured questions.

The user needs to setup the Secret Questions, for which the user needs to select the questions from a predefined set of questions and provide their relevant answers which the user can answer later when logging into the system.

<figure><img src="../../.gitbook/assets/image (519).png" alt=""><figcaption></figcaption></figure>

When the user logs in the next time user needs to answer these questions to be able to successfully login into Cymmetri

<figure><img src="../../.gitbook/assets/image (520).png" alt=""><figcaption></figcaption></figure>

Once successfully verified the user is redirected to the Dashboard

<figure><img src="../../.gitbook/assets/image (521).png" alt=""><figcaption></figcaption></figure>

## Configuration&#x20;

Cymmetri also allow you to customize the Secret Questions parameters using the Configuration section. Here you may configure the values as shown below:

**Required Questions To Configure:** Select the number of Secret Questions that users need to configure to set up for verifying the account. Default is 3.

**Minimum Correct Questions:** Choose the minimum number of questions that users need to answer correctly to gain access to their accounts or retrieve passwords. Default is 3.

**Minimum Answer Length:** Choose the minimum number of characters for the answer to these questions. Default is 2.

**Maximum Answer Length:** Choose the maximum number of characters for the answer to these questions. Default is 35.

<figure><img src="../../.gitbook/assets/image (522).png" alt=""><figcaption></figcaption></figure>

Administrators can create a predefined set of Secret Questions that users can choose from while setting up their Secret Question/Answer combinations as an added layer of protection for their Cymmetri accounts.&#x20;

To a new question Administrator needs to click on the "Add New" button and enter the following details:

**Question:** The question that the administrator wants to add

**Status:** needs to be enabled for the question to appear in the list

<figure><img src="../../.gitbook/assets/image (523).png" alt=""><figcaption></figcaption></figure>

Administrators can easily edit, delete, activate or deactivate Secret Questions in use.

<figure><img src="../../.gitbook/assets/image (524).png" alt=""><figcaption></figcaption></figure>
