# External Identity Provider Configuration - Azure IDP

#### Setting up Cymmetri Service Provider for External Identity Provider Configuration

The page [here ](../../service-provider.md)shows how to configure a Service Provider.

Navigate to External IDP in Identity Provider.

<figure><img src="../../../../.gitbook/assets/image (489).png" alt=""><figcaption></figcaption></figure>

Select Azure-IDP.

<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84016974038/original/bgagnzXTPsiYUya2t8RMZ-95EX6Pmk-ukA.png?1665069625" alt=""><figcaption></figcaption></figure>

Configure Azure AD for Creating Identity provider configuration

Now Login to the Azure portal and select Azure Active Directory.

<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84016974039/original/pB3MOVp9sPViaVsXIdBeD4Caaf6Okg2Ytg.png?1665069625" alt=""><figcaption></figcaption></figure>

Navigate to Enterprise applications and select New Application.

<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84016974048/original/9Mu--doH01hGLvDwvKKjOoupHPKGVOVYVQ.png?1665069629" alt=""><figcaption></figcaption></figure>

Create your own application and enter the name of the application.

<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84016974046/original/RTHeq895zsrnGYAf_8ZJXums4A8JxaSTQA.png?1665069629" alt=""><figcaption></figcaption></figure>

Set up Single Sign On after creating the application using SAML.

<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84016974052/original/8oZlOSNd-N9MqwjL_CPzNZKTrmI-aIqYxA.png?1665069632" alt=""><figcaption></figcaption></figure>

Click on Edit basic SAML configuration.

Add Identifier (Entity ID) and Assertion Consumer Service URL from the XML file downloaded in step 3  (For Azure, Sign on and ACS URL are the same) and save the configuration.

Download the Certificate (Base64) from SAML Certificates.

<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84016974054/original/IOfp9Cn8OZqpZnlg_b9tr34HuvFy4eocEQ.png?1665069634" alt=""><figcaption></figcaption></figure>

Continue configuration of Identity Provider In Cymmetri Administration Console&#x20;

Copy Azure AD Identifier from Set up,  navigate to azure-idp in Cymmetri, and paste it in Entity ID. Similarly, copy the login URL and paste it into the Single Sign On Service URL in Cymmetri.

Replace the text "\<host-name>" as the URL of the Cymmetri deployment (e.g., [https://aktestidp.ux.cymmetri.in](https://aktestidp.ux.cymmetri.in/)) "aktestidp.ux.cymmetri.in" in the _destination_ field - "https://_\<hostName>_/spsamlsrvc/samlSP/SingleSignOnService"  as "[https://aktestidp.ux.cymmetri.in/](https://aktestidp.ux.cymmetri.in/)spsamlsrvc/samlSP/SingleSignOnService".

Open the Base64 certificate downloaded in step 12, copy it, and then paste it into the x509Certifcate field in Cymmetri.

Select the created service provider in the Service Provider Id field dropdown and save the changes.

<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84016974055/original/Aqpu3G_w0RhjERSnsi0qyS6eqK4OgcAeUQ.png?1665069635" alt=""><figcaption></figcaption></figure>

For enabling Azure IDP to be used as an IDP for a specific set of users an Authentication Rule needs to be configured. [Here ](../../authentication-rules.md)you can see the steps on how to configure Authentication Rules.

#### Assigning Users

Assigning users to applications in Azure Administration Console to allow users to use Azure as an External Identity provider&#x20;

Navigate to Enterprise applications and select the application you created in step 8.

Go to Users and Groups, and select Add user/group and add the user.

<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84016974681/original/RQTvBewGfC-tBEH0UQGK2lT94IuP8QDezQ.png?1665070193" alt=""><figcaption></figcaption></figure>

#### Configuring JIT provisioning in Cymmetri Administration Console

If JIT provisioning needs to be enabled for Azure AD as external Identity provider, we may set it up using the steps below.&#x20;

Navigate to JIT in external identity provider and enable JIT Configuration.

The following fields are mandatory in Cymmetri - firstName, lastName, login, userType, displayName, and email.

For Azure JIT configuration, the following mapping needs to be done -&#x20;

1. First Name -&#x20;
   1. Application Field - http://schemas.xmlsoap.org/ws/2005/05/identity/claims/givenname
   2. Cymmetri Field - firstName
2. Last Name -
   1. &#x20;Application Field - http://schemas.xmlsoap.org/ws/2005/05/identity/claims/surname
   2. Cymmetri Field - lastName
3. Login (Username) -&#x20;
   1. Application Field - http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name
   2. Cymmetri Field - login
4. User Type -&#x20;
   1. Application Field - any string
   2. Cymmetri Field - userType
   3. Default Value - \<will be one of Employee, Vendor, Consultant>
5. Display Name -&#x20;
   1. Application Field - http://schemas.microsoft.com/identity/claims/displayname
   2. Cymmetri Field - displayName
6.  Email Address -&#x20;

    1. Application Field - http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name
    2. Cymmetri Field - email

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84016975236/original/-kYQOdugOno4XBFwoLTNtfj-MmySiadaSA.png?1665070744" alt=""><figcaption></figcaption></figure>

#### In Azure Administration Console&#x20;

Login to cymmetri using Azure Email Address

<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84016975393/original/MjIVhkF72jWARwsW0GO5o13CLB3tGMHLYA.png?1665070976" alt=""><figcaption></figcaption></figure>

The user will be redirected to the Azure portal to enter the Azure credentials.

<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84016976869/original/ahAfG5vERpt-8BFFfULPp6dzZJgC7_iAMg.png?1665072577" alt=""><figcaption></figcaption></figure>

Once the credentials have been entered properly in the Azure portal, the user will be redirected back to Cymmetri and will be logged in successfully.&#x20;

<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84016976884/original/POjIW5qnv4NLuJTw_iKjHYGbfwWtnj0pOw.png?1665072600" alt=""><figcaption></figcaption></figure>
