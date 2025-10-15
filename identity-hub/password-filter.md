# Password Filter

### Introduction <a href="#introduction-to-templates" id="introduction-to-templates"></a>

The Cymmetri Architecture without the password filter utility allows for one-way synchronization of passwords from Cymmetri to managed applications like Active Directory. Active Directory passwords may therefore be updated, once the user password is updated in Cymmetri.&#x20;

However, to keep both the Cymmetri database and Active Directory user passwords in synchronization, there is a need for Cymmetri database to receive password change notification from the Active Directory, when the password is directly updated in Active Directory.&#x20;

Active Directory provides for the use of Password Filter which can intercept the request for password change and can make an API call to Cymmetri to update the password in Cymmetri database as well.

### Flow Diagram <a href="#creating-templates" id="creating-templates"></a>

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84020662351/original/btLBcZ0aPK_aIaTaG6GM4zPVT0ytpr0FuQ.png?1669705796)

### Flow Description <a href="#creating-templates" id="creating-templates"></a>

1. Cymmetri Password Filter dll will be deployed in the Active directory environment and system variables (environment variables) are configured to allow the password filter to connect to the Cymmetri deployment.
2. Active Directory server needs to be restarted once the configuration is performed.
3. Once the user changes the password on a domain-connected computer using Ctrl+Alt+Delete utility OR if the Active Directory administrator resets the user's password using Active Directory tools, the password filter will be triggered.
4. The password filter DLL will receive the username and the plaintext password from the Active Directory, once the password change has been applied on the Active Directory.
5. The password filter DLL will encrypt the password using RSA encryption with a public key and will send the encrypted password and the username to the Cymmetri deployment using a REST API call over HTTPS.
6. The Cymmetri deployment receives the username and encrypted password, it decrypts the password using private key.
7. Once the password is decrypted, the Cymmetri deployment updates the password in Cymmetri database for the given user.&#x20;
8. If the user is assigned multiple applications for provisioning, the action of updating user's password in Cymmetri database will trigger password update for the user in other provisioned applications. However, Active directory application will not receive this password update, to avoid loops.

### Configuration <a href="#using-templates" id="using-templates"></a>

<table><thead><tr><th width="334">Key</th><th>Value</th></tr></thead><tbody><tr><td>CYMMETRI_APP_ID</td><td>&#x3C;application-id-of-active-directory-in-Cymmetri></td></tr><tr><td>CYMMETRI_CLIENT_TOKEN</td><td>Authorization: Bearer &#x3C;token-from-api-client><br></td></tr><tr><td>CYMMETRI_ENDPOINT_URL</td><td>https://&#x3C;cymmetri-domain>/apiext/api/password/filter/updateUserPassword</td></tr><tr><td>CYMMETRI_PUBLIC_KEY_FILE</td><td>&#x3C;path of public key file in Active Directory Server></td></tr></tbody></table>

## Steps for deploying Password Filter DLL&#x20;

1. Download the dll file and the public key file from here -\
   CPFv308.dll - https://drive.google.com/file/d/15uPQYnJr7HUWnxHLPSpYtsWGKkm5HnLC/view?usp=share\_link\
   public.pem - https://drive.google.com/file/d/1OdBLal4RTA5bMqABJEq3zQeLxNzSOE0R/view?usp=share\_link
2. Place the CPFv308.dll file in the C:\Windows\System32 folder.
3. Run regedit and go to the following path: HKEY\_LOCAL\_MACHINE\SYSTEM\CurrentControlSet\Control\Lsa
4.  You must now see a page similar to this:

    <figure><img src="https://lh6.googleusercontent.com/dYzqlA4N32Bc_JPXUuYs7EnlRamo-lsyOYVCLY_sY2qGTjDu24XadgxQ15VwOHZ2WZBFG8xiLMfaV5Eeau4QrKGhCfFkfFXibLaMO1EnQM-hIymJ4r4DhKGJEpDjpEoXJfFVfj2HQ3dFrkfJMB7YVxg" alt=""><figcaption></figcaption></figure>
5.  Select the element Notification Packages and double click it

    <figure><img src="https://lh4.googleusercontent.com/WYuaUzaIQlObouTS0D9v2kU1FFcxcnpAnBGvK6_4TTYHv1AsM-DlkTS0jhYSA509p0OsWdlvbeGIrXD98Zg8kpG1VIalu4c0PeQaXjefqlic82a6yPw_0EKa54Kdi9uOnU6U4nbhua45wKDMYakFm2o" alt=""><figcaption></figcaption></figure>


6. Add the line “CPFv308” and Click on OK to save the registry entry.
7. Exit the registry editor.
8. Save the public.pem file to any directory and note the name of the directory. Ex - C:\Users\Administrator\Desktop\public.pem
9. For testing the deployment, Login into the Cymmetri portal as an administrator and note the application ID of the Active Directory application configured for provisioning. Ex - 69125912519fb123
10. Also, create a new API client.

<figure><img src="https://lh4.googleusercontent.com/g76HqdGKIYLf3uccC7E0dXtf2HQvSMynGViA7-721L9joMjT664fbJlkzLJfN4DjdC1QNnlEn7P9_7STe3bSSrM1JEVwrqQlRhv-RBAQZ3e2e8OuAma71qBqRE2s9-qFIDgypChlCB9flFVnONsPf7Y" alt=""><figcaption></figcaption></figure>

11. Click on renew secret and note the bearer token generated.

<figure><img src="https://lh3.googleusercontent.com/vLHimXcBvPVimbgn2L3_k3AI4KDxty3iJL_vrIMXeKLxv7D98RoTS9RSPR0Nied2Y5f4E21Y720Dwuq4bM9TJH2KgI0lW-zpJKnVWJkdU99ufwGcPISgHkw_JDv7Ag5_QXdRLr2ZenTL301XPdOCo2c" alt=""><figcaption></figcaption></figure>

Ex - eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJOZXcgQVBJIENsaWVudCIsInRlbmFudCI6IjI3NyJ9.L\_q7I4MFcZSFXetdSvzD7hxvfcSrUUaJEkwhUTfHgus

12. Go to Control Panel > System > Advanced System Settings and click on environment variables.
13. Add the following System variables.
    1. Key = CYMMETRI\_APP\_ID; Value = \<application-id-of-active-directory>; Example = 6015991fdfeab12c
    2. Key = CYMMETRI\_CLIENT\_TOKEN; Value = Authorization Bearer \<token-from-api-client>; Example = Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJOZXcgQVBJIENsaWVudCIsInRlbmFudCI6IjI3NyJ9.L\_q7I4MFcZSFXetdSvzD7hxvfcSrUUaJEkwhUTfHgus
    3. Key = CYMMETRI\_ENDPOINT\_URL; Value = \<domain>/apiext/api/password/filter/updateUserPassword; Example = [https://277.newqa.cymmetri.in/apiext/api/password/filter/updateUserPassword](https://277.newqa.cymmetri.in/apiext/api/password/filter/updateUserPassword)
    4. Key = CYMMETRI\_PUBLIC\_KEY\_FILE; Value = \<path of public.pem file>; Example = C:\Users\Administrator\Desktop\public.pem
14. Save the environment variables.
15. Create a folder as C:\passfilter\_logs to store the logs.
16. Take a restart of the Active Directory Server.

### Configuring Password Filter in Cymmetri

1. Navigate to the Configuration Menu.
2. Look for the Password Filter option in the Configuration Menu.
3. Once on the page click on "+Add New" button
4. This will open the configuration page, You should find a toggle button to enable the Password Filter. Turn it on to enable the filter.
5. Once the Password Filter is enabled, you'll need to choose the filter type.There are two options: "Include" and "Exclude."
   1. "Include" means that only the applications selected in the included applications dropdown will receive synced passwords and have their passwords changed correspondingly.
   2. "Exclude" means that all applications except the ones selected in the excluded applications dropdown will receive synced passwords and have their passwords changed correspondingly.
6. Next you select the Filtered Application this is usually the managed application where the password changed has happened which in this case is Active Directory
7. Next, determine which type of authenticator you want to use for password synchronization.
   * You typically have three options: Cymmetri Authenticator, AD (Active Directory) Authenticator, or LDAP (Lightweight Directory Access Protocol) Authenticator.
   * Choose the appropriate authenticator based on your requirements and configuration.
8.  After completing the above steps, make sure to save your configuration settings.Click on the "Save" button to save your changes.

    <figure><img src="../.gitbook/assets/image (262).png" alt=""><figcaption></figcaption></figure>
