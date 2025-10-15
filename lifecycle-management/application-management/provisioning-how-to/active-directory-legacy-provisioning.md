# Active Directory (Legacy) Provisioning

> **Pre-requisites:**
>
> Make sure you have the following information before you proceed further:
>
> * Cymmetri login credentials
> * Access to IIS (Internet Information Services) to install certificates.
>   * Access to Windows Certificate Services
> *   Active Directory Essentials:
>
>     * Server hostname and password
>     * OU (Organisation Unit) name, if any
>     * SSL ports need to be enabled on your side
>     * Export the CA Certificate from Active Directory and import it into the Connector Server.
>     * Make sure the certificate is installed on the Connector Server
>
>

## Step 1 - Configure your Active Directory Certificate and export it to Connector Server

&#x20;For details on how to install ssl certificate in AD refer this link: [ https://www.manageengine.com/products/active-directory-audit/kb/how-to/how-to-install-ssl-certificates-in-active-directory.html](https://www.manageengine.com/products/active-directory-audit/kb/how-to/how-to-install-ssl-certificates-in-active-directory.html)

Exporting your Active Directory certificate to the Connector Server is a necessary and crucial step. This ensures that the Active Directory and Cymmetri Identity Server can communicate over LDAPS (LDAP over SSL). For this to happen, LDAPS requires a properly formatted certificate installed in your Active Directory Domain Controllers. Please refer to this link and follow the same steps: [https://www.manageengine.com/products/active-directory-audit/kb/how-to/how-to-install-ssl-certificates-in-active-directory.html](https://www.manageengine.com/products/active-directory-audit/kb/how-to/how-to-install-ssl-certificates-in-active-directory.html)

Once the certificate has been imported per the above instructions, you must restart the application to apply the changes made.

## Step 2 - Add a new Active Directory application to Cymmetri

*   Navigate to the Identity Hub on the left navigation bar and click the Applications tab. You will see a list of existing applications.&#x20;

    <figure><img src="../../../.gitbook/assets/image (150).png" alt=""><figcaption></figcaption></figure>
*   Click 'Add New', and you will find the entire list of all available applications.

    <figure><img src="../../../.gitbook/assets/image (151).png" alt=""><figcaption></figcaption></figure>
*   Search for Active Directory on the top right and click on it. You should see the Active Directory application sidebar on the right.

    <figure><img src="../../../.gitbook/assets/image (152).png" alt=""><figcaption></figcaption></figure>
* The `Application Label` has a default name for the Active Directory application and can be changed according to your choice. Click 'Add Application' from the bottom right to add the Active Directory application to your Cymmetri profile.

You have now added an Active Directory application to Cymmetri.

<figure><img src="../../../.gitbook/assets/image (153).png" alt=""><figcaption></figcaption></figure>

## Step 3 - Adding Policy Attributes

*   After adding the Active Directory, the 'Configure Now' button is enabled. Click this button to start setting up your Active Directory application.

    <figure><img src="../../../.gitbook/assets/image (154).png" alt=""><figcaption></figcaption></figure>
* Define which attributes should be fetched from your Active Directory. You can do that by going to the Policy Attribute section.
* Here below are shown some Active Directory attribute descriptions

| Attribute Name | Description                                                                          |
| -------------- | ------------------------------------------------------------------------------------ |
| CN             | Common Name/ Display Name                                                            |
| RDN            | Relative Distinguished Name - An RDN is the relative portion of a Display Name (DN). |
| SN             | Surname                                                                              |

<figure><img src="../../../.gitbook/assets/image (156).png" alt=""><figcaption></figcaption></figure>

> Policy Attributes - Policy attributes are user attributes (field names) in the Active Directory.&#x20;

* The policy attribute table is prefilled with standard Active Directory Attributes by default. Please verify if it works for you. If not, follow the below mappings for the provisioning to work.&#x20;

1. `telephoneNumber` - mobile
2. `sAMAccountName` - login
3. `givenName` - firstName
4. `mail` - email
5. `sn`- lastName
6. `cn` - firstName

2.1 Adding new attributes

* If the standard list does not contain the attributes you want to include, you can add new attributes by clicking the 'Add new' button on the right.&#x20;
*   Fill in the attribute name, and description and click Save.&#x20;

    <figure><img src="../../../.gitbook/assets/image (157).png" alt=""><figcaption></figcaption></figure>
*   Also, toggle the Active switch to enable this new attribute.

    <figure><img src="../../../.gitbook/assets/image (158).png" alt=""><figcaption></figcaption></figure>

Besides the present policy attributes, you need to add a custom attribute in case you're going for group provisioning, i.e. `memberOf` attribute.

## Step 4 -  Map your Active Directory Attributes to Cymmetri

* Now that you've defined what attributes to fetch from Active Directory, you will map these to Cymmetri user attributes.
* On the same window, navigate to the policy map in the left navigation bar.&#x20;

> Policy Map - Mapping of Cymmetri and Active Directory attributes.

<figure><img src="../../../.gitbook/assets/image (159).png" alt=""><figcaption></figcaption></figure>

* You will see that the attributes are set to `False` by default. Our first step in the mapping process is to enable the attributes for syncing.
*   Click on the edit button next to the 'Application Field' name.&#x20;

    <figure><img src="../../../.gitbook/assets/image (160).png" alt=""><figcaption></figcaption></figure>
* The 'Application Field' indicates the Active Directory field name, and the 'Cymmetri Field' indicates the Cymmetri field name.&#x20;
* To map the attributes, we need to sync the attributes on create and update only. Hence, these checkboxes need to be checked.&#x20;
* The 'Set default value' field accepts the default value you enter here if the field is empty in Active Directory.&#x20;
*   Next, click on the 'Update' button.

    <figure><img src="../../../.gitbook/assets/image (161).png" alt=""><figcaption></figcaption></figure>
* Similarly, repeat this for all attributes.
*   One exception is the `sAMAccountName` field. The 'Is User Principal' checkbox is enabled by default because it is the primary key (unique data) on the Active Directory side, and `login` is the primary key on Cymmetri side; leave it checked.&#x20;

    <figure><img src="../../../.gitbook/assets/image (162).png" alt=""><figcaption></figcaption></figure>

Some important policy map fields which need to be declared in the policy map are as follows.&#x20;

| Active Directory attribute | Cymmetri Attribute                           |
| -------------------------- | -------------------------------------------- |
| \_\_NAME\_\_               | Users Display Name                           |
| \_\_PASSWORD\_\_           | Users password                               |
| sAMAccountName             | Unique login attribute                       |
| cn                         | Unique login attribute (specific to user)    |
| rdn                        | Used to pass the OU (Organization Unit) path |

* If any attribute is missing from the policy map but present in your policy attribute. Add it by clicking the 'Add Cymmetri Field' and follow the same steps to map it to the appropriate field.
* If you want to add a new field that is not present even in Cymmetri, click on the 'Add Custom Field' button. For group provisioning, the `memberOf` attribute must be configured with the `memberOf` attribute from the custom attribute.

### Hook Configuration

Every organization has its own custom implementation scenarios such as duplicate checks for login id, emails and displaynames; similarly provisioning to specific AD OUs based on various conditions. Hooks allow to transform the data and execute the validation rules as per the custom implementation scenarios.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXcJVdID0NLz03xYcY9PbV7wCTp5D3Fsv7LoGPYAHtqhVRgrpGVBDhxj6L_ZbdA8n_bD8SFB0X_2WZbfIcilzxd0b-6tVaE4c481cZkxwuoGw3pMoD7xb7SOYmxiMFnC_Lde6Mj5jzOcfDllzhk-YbalzxStJxn9Mazi99H70vLJYM6ayzexNg?key=ES3-gdOFgPh8dn0zAQKG8w" alt=""><figcaption></figcaption></figure>

## Step 5 - Configure the Connector Server

*   The connector server is a tool that provides different connectors that enable various provisioning operations from different sources to Cymmetri. Below you may see that Cymmetri supports all the various lifecycle operations needed to seamlessly perform various user operations.

    <figure><img src="../../../.gitbook/assets/image (797).png" alt=""><figcaption></figcaption></figure>
* In our case, we will prepare the connector server to work with the Active Directory source.
*   Click Provisioning from the left navigation bar and enable application provisioning by sliding the slider button.

    <figure><img src="../../../.gitbook/assets/image (163).png" alt=""><figcaption></figcaption></figure>
*   Once you enable the application provisioning, you must take care of two configurations to successfully provision Active Directory data to Cymmetri.

    <figure><img src="../../../.gitbook/assets/image (164).png" alt=""><figcaption></figcaption></figure>

1. Server Configuration - Consists of configuring the connector server.&#x20;

* Enter the IP address of the host server and its password. The rest of the fields come pre-filled with default values; you can change them according to your use case.  Next, click on the save configuration button.

| Field Name                      | Description                                     |
| ------------------------------- | ----------------------------------------------- |
| Host server                     | The IP address of the host server               |
| Server port                     | Port of the host server                         |
| Server Password                 | Host Server password                            |
| Server connector bundle version | Version number of the connector server bundle   |
| Server connector bundle name    | Name of the connector server bundle             |
| Server connector name           | Given name of the connector server              |
| Server Connector Timeout        | Timeout of the connector server in milliseconds |
| Server Connector UseSSL         | Connector server SSL configuration              |

<figure><img src="../../../.gitbook/assets/image (587).png" alt=""><figcaption></figcaption></figure>

2. User Configuration - Consists of all user settings like domain name, search filter, etc. We can also configure an OU (Organisational Unit) in this window.&#x20;

| Field Name                           | Description                                                                                                                               |
| ------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------- |
| Entry object classes                 | Object classes to which the Account class is mapped                                                                                       |
| Root suffixes                        | Display names used for Active Directory synchronisation to Cymmetri, such as domain controller name                                       |
| Principal password                   | Admin password to connect to Active Directory                                                                                             |
| Default id Attribute                 | Default attribute Id                                                                                                                      |
| Custom user search filter            | Search filter used to search accounts                                                                                                     |
| Connector messages                   | Custom connector messages                                                                                                                 |
| Default group container              | Default group container can be used during create operation in case of entry DisplayName is not explicitly mentioned                      |
| Default people container             | Default people container can be used during create operation in case of entry DisplayName is not explicitly mentioned                     |
| Group owner reference attribute      | Group attribute referencing (by DisplayName) the users members of a group                                                                 |
| Custom group search filter           | User search filter for groups                                                                                                             |
| Group search scope                   | Choose object, onlevel or subtree                                                                                                         |
| Server hostname                      | Active Directory server hostname that would connect to Cymmetri                                                                           |
| Conservative membership policy       | Conservative management of assigned groups. The groups already assigned to an user on Active Directory will not be removed.               |
| Memberships                          | Groups to identify users to synchronize. The connector ignores any changes about users not member of indicated groups.                    |
| Verify memberships in OR             | Indicate if specified memberships must be verified using 'OR' logical operator.                                                           |
| Object classes to synchronise        | User object classes to synchronise. The connector ignores any changes if it cannot find modified entry object classes in this property.   |
| Page size                            | Get users from Active Directory with the provided size                                                                                    |
| Pageable result                      | Get users from Active Directory with the provided size pageable result                                                                    |
| Server port                          | Port of the Active Directory connector server                                                                                             |
| Principal                            | Admin username of the Active Directory                                                                                                    |
| Permit password update only          | <p>Permit password update only.</p><p>Create/delete operation will be denied, while other attributes update requests will be ignored.</p> |
| Retrieve deleted groups              | Indicate if deleted groups must be synchronized also.                                                                                     |
| Retrieve deleted users               | Indicate if deleted users must be synchronised also.                                                                                      |
| SSL                                  | True if the SSL certificate is configured                                                                                                 |
| Trust all certs                      | Indicative if all server certificates can be trusted                                                                                      |
| UID attribute                        | Unique Identifier Attribute                                                                                                               |
| Base context for user entry searches | Display the Name of OU (Organization Unit), Root domain or Root controller required for user entry search                                 |
| User search scope                    | The scope could be a subtree or object for user search                                                                                    |

<figure><img src="../../../.gitbook/assets/image (166).png" alt=""><figcaption></figcaption></figure>

> Note - You would need to change the below fields as per your organisation:
>
> 1. Root suffix - Add your domain name here.
> 2. Principal Password - Add your server password here.
> 3. Server Hostname - Add your server name here.
> 4. Principal - Add your admin Display Name of the Active Directory.
> 5. The base context for user search - You can add your Organisation Unit here.
> 6. The base context for group search - Add the base context to enable group search
> 7. Server port - Ensure that it is set to 636 for push
> 8. Page size- Define pageable result count for users
> 9. SSL - True is SSL is configured
> 10. Trust all certs - True.
> 11. Disable User OU Movement - Provide the path for disabling OU movement here.

Click on the save configuration button. Next, click on test configuration to see a successful toast message if your configuration is successful.

While configuring, you might encounter errors like:

* Authentication exception - Failure due to incorrect username and password.
  * Solution - Keep all your necessary credentials handy and enter the details carefully
* Socket timeout - Connection refusal by the target system
  * Solution - Please ensure your network connections are accurate to avoid socket timeout errors.
* SSL issue - SSL issue occurs mainly if certificates are not configured correctly.
  * Solution - Follow the steps mentioned in Step 1 rigorously to import the Active Directory certificate to avoid SSL-related errors.

## Step 6 - Start syncing users from Active Directory to Cymmetri

The last step of onboarding users is to add the users from Active Directory to Cymmetri by Reconciliation.

### Pull Reconciliation

Pull users from your Active Directory to Cymmetri.

*   Click the 'Reconciliation' tab on the left navigation bar on the same page.&#x20;

    <figure><img src="../../../.gitbook/assets/image (169).png" alt=""><figcaption></figcaption></figure>
*   Next, click the 'Add New' button under the pull tab.&#x20;

    <figure><img src="../../../.gitbook/assets/image (170).png" alt=""><figcaption></figcaption></figure>
* Add the field name details, and give a name to the pull reconciliation.&#x20;
  * The modes field is prefilled with 'FILTERED\_RECONCILIATION'; keep it as it is. It specifies the mode of Reconciliation.
  * The Sync fields are a drop-down menu with Cymmetri attributes that need to be mapped with the Source attributes, that is, your Active Directory attributes. Choose the correct mappings for these fields.
  * Keep the `Status` as Active.
  *   `Types` are prefilled with the `User`. Keep it as it is.

      <figure><img src="../../../.gitbook/assets/image (171).png" alt=""><figcaption></figcaption></figure>
* You can define the conditions for the Pull Reconciliation. It specifies the different scenarios of the Reconciliation. All the tabs have the same options in the dropdown: `IGNORE`, `UPDATE`, `DEPROVISION`, `PROVISION`, `UNLINK`, `LINK`, `ASSIGN`, `UNASSIGN`.

| Options     | Usage                                                          |
| ----------- | -------------------------------------------------------------- |
| IGNORE      | You can skip the process by choosing this option.              |
| UPDATE      | It can be used when you want to modify or reflect new changes. |
| PROVISION   | You can use this option to onboard the users.                  |
| DEPROVISION | You can use this option to remove the users.                   |
| LINK        | You can use this option to link the users to Cymmetri          |
| UNLINK      | You can use this option to unlink the users to Cymmetri        |
| ASSIGN      | You can use this option to assign the users to Cymmetri        |
| UNASSIGN    | You can use this option to unassign the users to Cymmetri      |

Here is an example scenario:

| User exists in target system, not in Cymmetri | User exists in both systems | User does not exist in target system, but in Cymmetri | Result                                                                                                                                            |
| --------------------------------------------- | --------------------------- | ----------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| UPDATE                                        | IGNORE                      | PROVISION                                             | Update user details in the target system, ignore if a user is present in both systems and provision users that do not exist in the target system. |

* The options to choose in a Reconciliation operation depend on your use case and change accordingly.
*   In this case, we have chosen to `IGNORE` the users that do not exist in your Active Directory but exist in Cymmetri. Also, `IGNORE` users who are present in both the systems. `PROVISION` the users that exist in your Active Directory but do not exist in Cymmetri.

    <figure><img src="../../../.gitbook/assets/image (172).png" alt=""><figcaption></figcaption></figure>
*   Hit the save button on the top left and click the 'Run now' button. The status of the recon changes to active.

    <figure><img src="../../../.gitbook/assets/image (173).png" alt=""><figcaption></figcaption></figure>
*   You can head to the users tab and check if users are synced. If the reconciliation is successful, the users start appearing in this tab.&#x20;

    <figure><img src="../../../.gitbook/assets/image (174).png" alt=""><figcaption></figcaption></figure>

### Push Reconciliation

Sync your user data to Active Directory.

*   Navigate to the push tab and click on 'Add New'.&#x20;

    <figure><img src="../../../.gitbook/assets/image (175).png" alt=""><figcaption></figcaption></figure>
*   Repeat Steps 2 and 3 from Pull Reconciliation.

    <figure><img src="../../../.gitbook/assets/image (176).png" alt=""><figcaption></figcaption></figure>
* Move towards the Search Filter and Add Criteria section on the page.
* Fill in all the user details like Department, Designation, User Type, Location, Manager, Group, if any, email and mobile number. Keep the account status slider in the unlocked option. Choose user status as 'Active'.&#x20;
*   Set the conditions for the Push Reconciliation.

    <figure><img src="../../../.gitbook/assets/image (177).png" alt=""><figcaption></figcaption></figure>
* Click on Save at the top-right corner of the page.
* Click on 'Run-now' to start the Push Reconciliation. You can check the status on the Reconciliation page.
* Navigate to the users page to check the new users added to Cymmetri.

### History

Navigate to the History tab to check and track the pull and push Reconciliation of the past.

<figure><img src="../../../.gitbook/assets/image (178).png" alt=""><figcaption></figcaption></figure>

Click on the eye icon to view the Push/Pull reconciliation operation.

<figure><img src="../../../.gitbook/assets/image (179).png" alt=""><figcaption></figcaption></figure>

All the details configured in the Push/Pull Reconciliation can be seen here. It also displays the Summary of Pending, Synced and Error records.

### Logs

If, in any case, you're facing issues, head to the **Logs->Audit Log** to check for error logs.&#x20;

<figure><img src="../../../.gitbook/assets/image (180).png" alt=""><figcaption></figcaption></figure>

* Click on the eye icon to check the event attributes in the audit log for errors.&#x20;

<figure><img src="../../../.gitbook/assets/image (181).png" alt=""><figcaption></figcaption></figure>





