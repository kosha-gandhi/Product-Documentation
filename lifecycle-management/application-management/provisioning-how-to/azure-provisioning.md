# Azure Provisioning

Azure provisioning in Cymmetri involves setting up configurations to automate the creation and management of user accounts in Microsoft Entra ID. This allows for seamless user onboarding and offboarding processes.

To implement Azure provisioning in Cymmetri, follow these general steps:

The administrator needs to login to Azure Portal: https://portal.azure.com&#x20;

<figure><img src="../../../.gitbook/assets/image (636).png" alt=""><figcaption></figcaption></figure>

Once logged in click on **More services->** button

<figure><img src="../../../.gitbook/assets/image (637).png" alt=""><figcaption></figcaption></figure>

In the next screen click on **Identity** -> **App registrations** inside the **Identity management** section

<figure><img src="../../../.gitbook/assets/image (642).png" alt=""><figcaption></figcaption></figure>

Next click on **New registration** to register a new App. Registering your application establishes a trust relationship between your app and the Microsoft identity platform. The trust is unidirectional: your app trusts the Microsoft identity platform, and not the other way around. Once created, the application object cannot be moved between different tenants.

<figure><img src="../../../.gitbook/assets/image (641).png" alt=""><figcaption></figcaption></figure>

Next enter the **Application Name** and select the Supported account types to organizational directory only : **Accounts in this organizational directory only (Cymmetri Organization only - Single tenant)** and then click on **Register**

<figure><img src="../../../.gitbook/assets/image (643).png" alt=""><figcaption></figcaption></figure>

Once registered next click on **Authentication** menu and **+Add a platform**.

<figure><img src="../../../.gitbook/assets/image (656).png" alt=""><figcaption></figcaption></figure>

On the next screen select **Mobile and desktop applications**

<figure><img src="../../../.gitbook/assets/image (657).png" alt=""><figcaption></figcaption></figure>

&#x20;Enter a **Custom redirect URIs:**  _http://localhost_ and click on Configure

<figure><img src="../../../.gitbook/assets/image (659).png" alt=""><figcaption></figcaption></figure>

Further enable the **Public Client flows** and click on **Save** button

<figure><img src="../../../.gitbook/assets/image (660).png" alt=""><figcaption></figcaption></figure>

Next go to **Certificates and secrets** menu and create a new client secret:

<figure><img src="../../../.gitbook/assets/image (645).png" alt=""><figcaption></figcaption></figure>

Next enter a **Description** for the and select the duration after which the secret would **Expire** -Recommended is 180 days (6 months) but can be changed as per the need. Once both the details are entered click on **Add** button

<figure><img src="../../../.gitbook/assets/image (646).png" alt=""><figcaption></figcaption></figure>

Next copy and save the Client Secret ID and Client Secret Value in a safe and accessible place. Client secret values cannot be viewed, except for immediately after creation. Be sure to save the secret when created before leaving the page.

<figure><img src="../../../.gitbook/assets/image (647).png" alt=""><figcaption></figcaption></figure>

Once the client secret details are stored next click on **API permissions** menu and then + **Add a permission**

<figure><img src="../../../.gitbook/assets/image (648).png" alt=""><figcaption></figcaption></figure>

On this page select **Microsoft Graph**

<figure><img src="../../../.gitbook/assets/image (649).png" alt=""><figcaption></figcaption></figure>

On the next page we require permissions for both **Delegated and Application permissions.** Select each type of permission and in that Search and select the following permissions/scopes:

1. APIConnectors.Read.All
2. Directory.ReadWrite.All
3. OpenID (Not available for Application Permissions)
4. PrivilegedAccess.Read.AzureAD
5. User.ReadWrite.All
6. Directory.Read.All

<figure><img src="../../../.gitbook/assets/image (653).png" alt=""><figcaption></figcaption></figure>

Once all the permissions are added a warning is shown: <mark style="color:red;">"You are editing permission(s) to your application, users will have to consent even if they’ve already done so previously."</mark> The administrator needs to click on the "Grant admin consent for Cymmetri Organization" link

<figure><img src="../../../.gitbook/assets/image (654).png" alt=""><figcaption></figcaption></figure>

On the click of the link a popup appears to grant admin consent, click on **Yes**

<figure><img src="../../../.gitbook/assets/image (655).png" alt=""><figcaption></figcaption></figure>

Next click on **Expose an API** and then click on **Add** to add an **Application ID URI**: The Application ID URI, also called identifier URI, is a globally unique URI used to identify the web API. This URI is the prefix for scopes in the Oauth protocol. You can either use the default value in the form of api://, or specify a more readable URI.

<figure><img src="../../../.gitbook/assets/image (662).png" alt=""><figcaption></figcaption></figure>

On the next page keep the default values intact and click on **Save** button

<figure><img src="../../../.gitbook/assets/image (663).png" alt=""><figcaption></figcaption></figure>

Finally you can see the **Overview** page that contains all the information you need to configure Azure in Cymmetri.

<figure><img src="../../../.gitbook/assets/image (669).png" alt=""><figcaption></figcaption></figure>

Also the User config Application Authority can be obtained from the endpoint section in the Overview page:

<figure><img src="../../../.gitbook/assets/image (670).png" alt=""><figcaption></figcaption></figure>

This completes the Azure side of the configuration, next the administrator needs to need to move to Cymmetri and configure the Azure application. Mentioned below are the steps required to configure Azure in Cymmetri:

Add a new Azure application **Identity Hub->Applications** and then click on the **+Add New** button

<figure><img src="../../../.gitbook/assets/image (664).png" alt=""><figcaption></figcaption></figure>

Once added the administrator needs to go to Policy Attribute section and ensure all the below mentioned attributes are present (Add if not already present):

* mailNickname
* displayName
* \_\_PASSWORD\_\_
* \_\_NAME\_\_
* userPrincipalName
* givenName
* surname
* mail
* usageLocation

<figure><img src="../../../.gitbook/assets/image (665).png" alt=""><figcaption></figcaption></figure>

Next the administrator needs to go to the Policy Map section and ensure a mapping shown as below is created:

<table><thead><tr><th width="202">Application Field</th><th width="143">Field</th><th width="134">User Principal</th><th width="124">Create Only</th><th>Update Only</th></tr></thead><tbody><tr><td>displayName</td><td>displayName</td><td>-</td><td>True</td><td>True</td></tr><tr><td>__NAME__</td><td>login</td><td>-</td><td>True</td><td>True</td></tr><tr><td>__PASSWORD__</td><td>password</td><td>-</td><td>True</td><td>True</td></tr><tr><td>mailNickname</td><td>mailNickName</td><td>-</td><td>True</td><td>True</td></tr><tr><td>userPrincipalName</td><td>login</td><td>True</td><td>True</td><td>True</td></tr><tr><td>givenName</td><td>firstName</td><td>-</td><td>True</td><td>True</td></tr><tr><td>surname</td><td>lastName</td><td>-</td><td>True</td><td>True</td></tr><tr><td>mail</td><td>email</td><td>-</td><td>True</td><td>True</td></tr><tr><td>usageLocation</td><td>country</td><td></td><td>True</td><td>True</td></tr><tr><td>azureLicense</td><td>azureLicense</td><td>&#x3C;actual license key></td><td>True</td><td>True</td></tr></tbody></table>

Once the policy map is created next the administrator needs to go to  Provisioning section and then to **Server Configuration** and need to configure the connector server as shown below:

<figure><img src="../../../.gitbook/assets/image (667).png" alt=""><figcaption></figcaption></figure>

Once the Server Configuration is done next the administrator needs to implement User Configuration with the below mentioned fields:

* User config Application Authority: This is the authority under which the application operates. For example, if you're using Azure AD, the application authority might be `https://login.microsoftonline.com/<tenant_id>/oauth2/authorize`
* User config application client id: This is the unique identifier for your application. It is provided by Azure when you register your application. For example, `e9a5a8b6-8af7-4719-9821-0deef255f68e`.
* Client Secret: This is a secret key used by the application to prove its identity when requesting access tokens. It should be kept confidential. For example, `7f7df45a-251e-49d3-a396-748bf8e05a3c`.
* User config domain: This is the domain associated with your Azure AD. For example, `contoso.onmicrosoft.com`.
* User config base password: This is the base password used for your application. For example, `MyBasePassword123`.
* Redirect URI: This is the URI to which Azure AD will redirect the user after authentication. For example, api://05b765c3-d64f-7704-b0d8-5c4c6bc674df
* User config resource URI: This is the URI of the resource (API, web app, etc.) that the application wants to access. For example, `https://graph.microsoft.com`.
* Azure Tenant ID: This is the identifier for your Azure AD tenant. For example, `72f988bf-86f1-41af-91ab-2d7cd011db47`.
* User config base username: This is the base username used for your application. For example, `MyUsername@contoso.onmicrosoft.com`.

<figure><img src="../../../.gitbook/assets/image (671).png" alt=""><figcaption></figcaption></figure>

Once the configuration is done and saved, Next click on **TEST CONFIGURATION** to test if Cymmetri is able to connect to Azure Server.

### Assign various Product Licenses to user

For assigning any sort of licenses to a user of various products two main policy map entries need to done as shown below:

* azureLicense: Need to provide license key for the product you wish to assign to the user
* usageLocation: This field needs a two-letter country code (ISO standard 3166). Required for users that are assigned licenses due to legal requirements to check for availability of services in countries. Examples include: `US`, `JP`, and `IN`.

<figure><img src="../../../.gitbook/assets/image (675).png" alt=""><figcaption></figcaption></figure>

The value for azureLicense can be obtained as explained below:

Go to [https://admin.microsoft.com/](https://admin.microsoft.com/) and login using the admin credentials. Once logged in go to **Billing->Licenses->Microsoft Teams Exploratory**

<figure><img src="../../../.gitbook/assets/image (676).png" alt=""><figcaption></figcaption></figure>

Once you click that it opens the page from which we can copy the product id from URL as shown below:

<figure><img src="../../../.gitbook/assets/image (678).png" alt=""><figcaption></figcaption></figure>

Once all the above configuration is done, on the same page in Cymmetri go to **Assignments section** and assign users to the application and ensure that these users are created in Azure's Microsoft Entra ID along with the Microsoft Teams license.

