# External Identity Provider Configuration - Google IDP

### Google Configuration:

1.  Log in to your Google admin account and go to the **Admin Section** as shown below:

    <figure><img src="../../../../.gitbook/assets/image (474).png" alt=""><figcaption></figcaption></figure>

Once in the admin section click on **Apps** > **Overview**

<figure><img src="../../../../.gitbook/assets/image (475).png" alt=""><figcaption></figcaption></figure>

In the overview page click on the **Web and mobile apps** tile to add a new custom app

<figure><img src="../../../../.gitbook/assets/image (476).png" alt=""><figcaption></figcaption></figure>

On the Web and mobile apps page click on the **Add app** dropdown and then select **Add custom SAML app** to add the Cymmetri tenant as a custom app

<figure><img src="../../../../.gitbook/assets/image (477).png" alt=""><figcaption></figcaption></figure>

Provide a relevant **App Name**, Optionally a **description** for the application can be provided. An **App Icon** can also be attached if required. Once entered click on the **Continue** button

<figure><img src="../../../../.gitbook/assets/image (478).png" alt=""><figcaption></figcaption></figure>

On the Google Identity Provider Detail page download the metadata file by clicking on the **DOWNLOAD METADATA** button. This metadata file needs to be used to get Entity ID, SSO URL, and Certificate. Administrators can download the certificate here or later as shown [here](external-identity-provider-configuration-google-idp.md#download-idp-certificate). Once downloaded click on **Continue**.

<figure><img src="../../../../.gitbook/assets/image (479).png" alt=""><figcaption></figcaption></figure>

Once the IDP metadata and certificate are obtained the Service Provider(i.e. Cymmetri) details need to be provided. We need to provide the **ACS URL** and the **Entity ID** these details can be obtained from Cymmetri as shown here. No change needs to be done for the Name ID format and Name ID, it can be kept to **UNSPECIFIED** and **Basic Information > Primary email**. Once done click on **Continue**

<figure><img src="../../../../.gitbook/assets/image (480).png" alt=""><figcaption></figcaption></figure>

Attributes can be added on this screen which could then be sent as a SAML response to Cymmetri. These values can be used to create a user in Cymmetri if JIT provisioning is enabled on Cymmetri's side

Group membership information can also be sent by configuring groups here and if the user belongs to the configured group. Once attributes and groups are configured click on **FINISH.**

<figure><img src="../../../../.gitbook/assets/image (481).png" alt=""><figcaption></figcaption></figure>

Once you click on the FINISH button the below screen appears that shows the configuration details. It also shows various shortcuts to **Test SAML Login, Download Metadata, Edit Details, and Delete the App**

<figure><img src="../../../../.gitbook/assets/image (482).png" alt=""><figcaption></figcaption></figure>

### Download IDP Certificate

If the administrator does not download the certificate while configuring the custom application, it can be later downloaded. For the same the administrator needs to go to **Security>Authentication>SSO with SAML applications.** This will open the Security Settings page from where either the IDP details like SSO URL and Entity ID can be copied and the IDP Certificate can be downloaded. These details can be used to configure the IDP in Cymmetri.

<figure><img src="../../../../.gitbook/assets/image (483).png" alt=""><figcaption></figcaption></figure>

### **Cymmetri Configuration**

Once Google IDP is configured, the administrator must proceed with the configuration on the Cymmetri side. To achieve this, the administrator needs to set up Cymmetri as a Service Provider and also incorporate Google as an external IDP.

The page [here ](../../service-provider.md)shows how to configure a Service Provider.

Once the Service Provider is configured, we need to configure Google as an external IDP.

Administrator needs to go to **Authentication->Identity Provider->External IDP.** Here you may either configure the already created **google-idp** instance or **+Add New**

<figure><img src="../../../../.gitbook/assets/image (487).png" alt=""><figcaption></figcaption></figure>

In either cases a screen opens where you need to provide the below mentioned details

* **Name**: Google IdP
* **IDP Type**: Google
* **Entity ID**: https://accounts.google.com/o/saml2?idpid=xxxxxxxxxxxx
* **SSO Service URL**: https://accounts.google.com/o/saml2/idp?idpid=xxxxxxxxxxxx
* **Destination**: https://\<hostname>/spsamlsrvc/samlSP/SingleSignOn
* **Protocol Binding**: HTTP Post (can also be set to HTTP Redirect if it is set so in Google IDP)
* **Name ID Policy**:
  * **Policy**: Email (This may change based on what is configured in Google IDP)
  * **Value**: Email (This may change based on what is configured in Google IDP)
* **Certificate**: Certificate downloaded from Google IDP
* **Logout Request URL:** Need to mention the SingleLogoutService url from the metadata file if SLO (Single Logout) is configured in Google.
* **Logout Protocol Binding:**&#x48;TTP Post (can also be set to HTTP Redirect if it is set so in Google IDP)
*   **Service Provider Id:** cymmetri (Need to the select the configured Service Provider as shown above)

    <figure><img src="../../../../.gitbook/assets/image (488).png" alt=""><figcaption></figcaption></figure>

Once all the details are entered Save the changes.

For enabling Google IDP to be used as an IDP for specific set of users an Authentication Rule needs to be configured. [Here ](../../authentication-rules.md)you can see the steps on how to configure Authentication Rules.

Once the rule is configured whenever a user matches with the rule conditions the user is redirected to Google screen and the user needs to provide his/her Google credentials to be able to login into Cymmetri.
