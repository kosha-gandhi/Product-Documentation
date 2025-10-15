# Vaulting Configuration

Vaulting Configuration section allows you to configure various details about vaults that are necessary for proper and efficient usage of vault users

It allows you to configure the following:

1. Password Policy
2. Active Directory (A central location for vault users)
3. Manual Generation of Passwords for Vault Users (All or Specific Users)

**Password Policy**

1. Cymmetri allows you to select a specific Password Policy for Vault Users, If nothing is changed it uses the default password policy of Cymmetri.
2.  For Changing the Password Policy for Vault Users, Select Vaulting Configuration and then select the Password Policy that you wish to implement from the dropdown provided as shown below:

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84027734126/original/nevTKKUEYD3lqcasl2__pR6Jrd_mJmEbSg.png?1677825348" alt=""><figcaption></figcaption></figure>

**Active Directory**

1. If the vault users are stored at a central location like Active Directory then we need to configure the location and access credentials of this Active Directory.&#x20;
2. For configuring the Active Directory we need to provide the following information as shown below:
   1. Active Directory Domain: Here we need to provide the Active Directory LDAP URL and the root domain details. For e.g. _ldaps://EC2AMAZ-2LBJU5A.cymmetri.in:636;DC=cymmetri,DC=in_
   2. User Name: This is the Active Directory Administrative username. For e.g. _Cymmadmin_
   3.  Password: This is the Active Directory Administrative password.

       <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84028159095/original/X_tl2bLlJLla0WDAkjbhCZG90w8FcCaHuQ.png?1678254466" alt=""><figcaption></figcaption></figure>

**Generation of Passwords for Vault Users (All or Specific Users)**

For Generating Password for Vault User we need to do the following configurations:

1. One or more users who will receive an email that contains the list of usernames and passwords&#x20;
2. Password for opening the file which contains the list of usernames and passwords
3. Configure a scheduler to reset the password of users and send an email to the above configured use
4. Manually send the list of usernames and passwords of all or specific users

\


**One or more users who will receive an email that contains the list of usernames and passwords:**

For adding users who will receive the email containing the list of usernames and passwords we need to select one more cymmetri users here as shown below:

<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84028159261/original/sntoszZmJccQwKfI_9DqEZS3vo6U_M0Z-g.png?1678254577" alt=""><figcaption></figcaption></figure>

\


**Password for opening the file which contains the list of usernames and passwords**

For Configuring the password simply enter the password in the password box provided

<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84028159295/original/iqUrHg6cBzoWw3kOzFmGrc-tssohzbmq4A.png?1678254624" alt=""><figcaption></figcaption></figure>

\


**Configure a scheduler to reset the password of users and send an email to the above configured use**

For configuring a schedular we need to enable the scheduler and provide the following details:

* A start execution date and&#x20;
*   cron expression

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84027741934/original/44v-rKPdO8K6ngprAXDWbHeTibrgCvv_rA.png?1677829095" alt=""><figcaption></figcaption></figure>

The cron expression can also be generated using the Generate Cron Expression option as shown below:

<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84027742047/original/yTI5ZYzrYE5Y5zeYF0tuhncoFHnzj0PZPw.png?1677829170" alt=""><figcaption></figcaption></figure>

\


**Manually reset and send the list of usernames and passwords of all or specific users**

* Password of vault users can be reset manually and sent an email for all or for specific users&#x20;
*   You can either reset password for all users and send a list by selecting the **All users** option and clicking on **Generate Password** button as shown below:

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84027743506/original/JaXxwoL1X4L7rwS0pmwikYM2gZ-DAfKwVw.png?1677829944" alt=""><figcaption></figcaption></figure>
*   Alternatively you may also send a list of only specific usernames and passwords by selecting **To specific users** option and then selecting the users whose details you need to reset and send.

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84027751968/original/tOUYtLuGTzXtxfNmwKrN0dsI-AGwAhk_TQ.png?1677835259" alt=""><figcaption></figcaption></figure>
