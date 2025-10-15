# Password Policy

## What is a Password Policy?

A password policy is a set of rules and requirements established by an organization or system to govern how users create and manage their passwords.&#x20;

The purpose of a password policy is to enhance security by promoting the use of strong, unique passwords and minimizing the risk of unauthorized access.

In Cymmetri, only the admin can create a password policy bby navigating to the authentication section and then in password policy.&#x20;

Upon landing the user can view a default Cymmetri password policy which cant be deleted or deactivated.

<figure><img src="../../.gitbook/assets/image (496).png" alt=""><figcaption></figcaption></figure>

To create a new password policy, the admin clicks on the add new button on the top right corner of the page.&#x20;

The user has to fill in the password policy form with the below details

1. **Policy Name** - Name of the policy
2. **Description**
3. **Conditional attribute type** - Default - User (Non modifiable)
4. **Conditional attribute Name** - Default - User Type (Non modifiable)
5.  **Conditional attribute value  -** ( Consultant, Employee, Vendor)

    <figure><img src="../../.gitbook/assets/image (497).png" alt=""><figcaption></figcaption></figure>

After saving the detail, a new password policy is created. The next step is to define the password policy. This is done by clicking on the edit button in front of the record.&#x20;

The admin can define the composition of the password. By rejecting

1. Password equals Password&#x20;
2. Password which equals to LoginID&#x20;
3. Password which equals to first or Last Name
4.  Blacklisted Password&#x20;

    <figure><img src="../../.gitbook/assets/image (498).png" alt=""><figcaption></figcaption></figure>

The admin can also establish the following parameters

1. Numeric characters minimum count
2. Password Length
3. Special characters count
4. Password History versions
5. Alpha characters&#x20;
6. Uppercase characters
7. Lowercase characters
8. Characters not allowed in the password&#x20;

In the "change" subsection the admin can also define:

1. Password expiration days
2. Password expiration warning from (no of days)
3.  Whether to change password on reset

    <figure><img src="../../.gitbook/assets/image (499).png" alt=""><figcaption></figcaption></figure>

## Blacklisted Password

The administrator also has the capability to set prohibited passwords, preventing users from using those specific passwords.

<figure><img src="../../.gitbook/assets/image (500).png" alt=""><figcaption></figcaption></figure>
