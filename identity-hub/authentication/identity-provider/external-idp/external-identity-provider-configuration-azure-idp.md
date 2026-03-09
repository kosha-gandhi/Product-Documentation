# External Identity Provider Configuration - Azure IDP

#### Service Provider Configuration

The page [here ](../../service-provider.md)shows how to configure a Service Provider.

#### Microsoft Entra Configuration

Now Login to the Microsoft Entra portal, [https://entra.microsoft.com/](https://entra.microsoft.com/)

<figure><img src="../../../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

Navigate to Enterprise applications and select New Application.

<figure><img src="../../../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

Click on Create your own application, Enter the Application Name and click on the Create button.

<figure><img src="../../../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

Once the application is created click on the Single Sign On  menu and Set up Single Sign-On with SAML

<figure><img src="../../../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

Download a metadata file from Cymmetri- Service Provider page (how to create service provider is shown above)

<figure><img src="../../../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

Upload the downloaded metadata file here:

<figure><img src="../../../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

The Identifier (Entity ID) and Assertion Consumer Service URL from the XML file downloaded in  previous step are populated, then save the configuration.

<figure><img src="../../../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

Download the Certificate (Base64) from SAML Certificates.

<figure><img src="../../../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

#### Assigning Users to the Application

Assigning users to applications in Microsoft Entra Enterprise Application that we just created to allow users to use Azure(Microsoft Entra) as an External Identity provider&#x20;

Navigate to Enterprise applications and select the application you created above

Go to Users and Groups, and select Add user/group and add the user.

<figure><img src="../../../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

#### Cymmetri IDP Configuration

Navigate to External IDP in Identity Provider.

<figure><img src="../../../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

Select Azure-IDP.

<figure><img src="../../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

Configure Azure AD for Creating Identity provider configuration

<figure><img src="../../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

Next, Continue the configuration of Identity Provider In Cymmetri Administration Console, copy Microsoft Entra Identifier from Set up,  navigate to azure-idp in Cymmetri, and paste it in Entity ID.&#x20;

<figure><img src="../../../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

Similarly, copy the login URL and paste it into the Single Sign On Service URL in Cymmetri.

Replace the text "\<host-name>" as the URL of the Cymmetri deployment (e.g., [https://aktestidp.ux.cymmetri.in](https://aktestidp.ux.cymmetri.in/) in the _destination_ field - "https://_\<hostName>_/spsamlsrvc/samlSP/SingleSignOnService"  as "[https://aktestidp.ux.cymmetri.in/](https://aktestidp.ux.cymmetri.in/)spsamlsrvc/samlSP/SingleSignOnService".

Open the Base64 certificate downloaded in step 12, copy it, and then paste it into the x509Certifcate field in Cymmetri.

<figure><img src="../../../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

Select the created service provider in the Service Provider Id field dropdown and save the changes.

<figure><img src="../../../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

For enabling Azure IDP to be used as an IDP for a specific set of users an Authentication Rule needs to be configured. [Here ](../../authentication-rules.md)you can see the steps on how to configure Authentication Rules.

#### Configuring JIT provisioning in Cymmetri&#x20;

If JIT provisioning needs to be enabled for Azure AD(Microsoft Entra) as external Identity provider, we may set it up using the steps below.&#x20;

Navigate to JIT in external identity provider and enable JIT Configuration.

<figure><img src="../../../../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

The following fields are mandatory in Cymmetri - firstName, lastName, login, userType, displayName, and email.

<figure><img src="../../../../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

For Azure JIT configuration, the following mapping needs to be done -&#x20;

| Label            | Application Field                                               | Cymmetri Field |
| ---------------- | --------------------------------------------------------------- | -------------- |
| First Name       | http://schemas.xmlsoap.org/ws/2005/05/identity/claims/givenname | firstName      |
| Last Name        | http://schemas.xmlsoap.org/ws/2005/05/identity/claims/surname   | lastName       |
| Login (Username) | http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name      | login          |
| User Type        | any string                                                      | userType       |
| Display Name     | http://schemas.microsoft.com/identity/claims/displayname        | displayName    |
| Email Address    | http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name      | email          |

#### Checking the Azure Authentication

Login to cymmetri using Azure Email Address

<figure><img src="../../../../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

The user will be redirected to the Azure portal to enter the Azure credentials.

<figure><img src="../../../../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

Once the credentials have been entered properly in the Azure portal, the user will be redirected back to Cymmetri and will be logged in successfully.&#x20;

<figure><img src="../../../../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>
