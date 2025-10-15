# SAML 2.0 Based SSO

_Note: To use this mechanism, please ensure that your managed application supports authentication using SAML 2.0 protocol acting as the Service Provider (SP)._

SAML 2.0 is a primarily web-based Single Sign On mechanism that uses XML based messages exchanged between the _authenticating party_, referred to as the **Identity Provider (IdP)** in the SAML 2.0 terms, and the _relying party_, referred to as the **Service Provider (SP)** in the SAML 2.0 terms.&#x20;

In the context of Cymmetri SAML 2.0 implementation, your Cymmetri platform acts as the Identity Provider (IdP) and the managed application that the end-user wishes to access through Single Sign On acts as the Service Provider (SP).&#x20;

### **SAML 2.0 bindings**

The mechanisms within the SAML 2.0 protocol used for sharing Single Sign On messages are referred to as the **SAML 2.0 bindings**.&#x20;

While the SAML 2.0 and its predecessor SAML 1.1 support various bindings, the Cymmetri platform supports the two most commonly used bindings for web applications - viz., **HTTP POST Binding** and **HTTP Redirect Binding**. These reflect the manner in which the requests and responses are shared between the Identity provider (Cymmetri platform) and the Service Provider (managed application).

**HTTP Redirect Binding:** The SAML assertion messages (request and response XML messages) are shared as _GET_ query parameters.

**HTTP POST Binding:** The SAML assertion messages (request and response XML messages) are shared as _POST_ body messages.

### SAML 2.0 Request-Response Cycle

Additionally, there are two flows in which SAML 2.0 Request-Response cycle may be accomplished.

1. Service Provider initiated flow (SP initiated flow)
2. Identity Provider initiated flow (IdP initiated flow)

To start the configuration of the managed application for SAML 2.0 based SignOn mechanism, we must identify the flow supported by the managed application.

Let us explore what both these flows mean and how to configure your managed application to use them.

### Service Provider Initiated Flow (SP Initiated Flow)

The SAML 2.0 Service Provider Initiated flow indicates that the Service Provider (in our case, the managed application which the end-user wishes to access via Single Sign On) has started the SAML 2.0 Single Sign On process by sending a SAML 2.0 request XML to the Cymmetri platform. This is achieved by the user landing on the Single Sign On URL of the managed application.&#x20;

In practice, however, since the user is typically on the Cymmetri platform, we have enabled mechanisms to redirect the user to the Single SignOn URL of the managed application, when the user clicks on the application tile.\


<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003448986/original/fL7_kRe0B-96XJwH90w5fD5sGo7gIeFaRA.png?1649356880" alt=""><figcaption></figcaption></figure>

**Flow Description**

1. User lands on the SSO URL page of the managed application. This may be either through clicking on the application tile on the Cymmetri platform or by the user actually entering the SSO URL of the managed application in the browser address bar.
2. Managed application generates the SAML 2.0 request XML which holds the following important parameters - Request Id, Assertion Consumer Service URL (ACS), the expected Protocol Binding, and the Issuer of the Request.
3. A redirect is made to the page handling Single Sign On requests on the Cymmetri platform (`<baseurl-of-cymmetri-tenant/samlsrvc/SingleSignOnService>`) with the request in base64 format as a query parameter.
4. This page sends the SAML request body to the backend services of the Cymmetri platform to validate the request and to verify whether a session exists for a Cymmetri user in the current browser instance.
5. If a session does not exist for any user, the user is asked to login into the Cymmetri Identity platform.
6. If a session exists for the user, then the backend validates whether the user is authorized to access the application for which the SSO request has been initiated. (by checking whether the user is assigned the application.)
7. The backend services of the Cymmetri platform generates a SAML response XML body and send it as GET request query parameter (if the protocol binding in the SAML request is HTTP Redirect) or as a POST request body (if the protocol binding in the SAML request is HTTP POST binding) to the Assertion Consumer Service URL mentioned in the SAML Request body, with the SAML Response audience as the Issuer mentioned in the SAML request body, and a field “InResponseTo” as the Request ID from the SAML request body.
8. The managed application would then validate the SAML response (and the signature, if was requested in the SAML request body).&#x20;
9. If the SAML Response body is not a valid SAML Response, then the user is redirected to the managed application’s error page.
10. If the SAML response body is a valid SAML response, then the SAML assertion is extracted to obtain the user information sent by the Cymmetri platform.
11. If the user information is not valid, for any reason, then the corresponding error is displayed to the user by redirecting the user to the managed application’s error page.
12. If all the user information is valid, the managed application initiates the user’s session in the managed application web portal, and corresponding session cookies are generated.
13. Finally, the user is redirected from the application’s Assertion Consumer Service URL to the landing page of the managed application.

_Note: In case of any validation errors, please refer to the section explaining the error scenarios below and change the configuration in either the managed application or the Cymmetri Application Sign On configuration page._

### Service Provider(SP) Initiated Flow Configuration

The configuration parameters mentioned below are required to configure an application for Single Sign On using the Service Provider Initiated flow in the Cymmetri platform.

**Prerequisites from the Managed Application**

1. **Entity ID/ Request Issuer** - This is the request issuer that would have been sent by the managed application in case this were a Service Provider Initiated flow.
2. **Assertion Consumer Service URL** - This is the URL to which the SAML response must be sent by the Cymmetri platform.
3. **Expected NameID Policy** - This indicates whether the managed application expects the user subject name to be sent as the email address, username, or some other unspecified value.
4. **Expected Signature Algorithm** - The expected algorithm to be used for signing the responses and assertions.

**Let us see an example demonstrating SP Initiated flow. We will be using a Service Now Instance for this example.**

Initially, we include a SAML service provider from the Single Sign-On section under Service Providers by selecting the "Add New" button located at the top right corner of the pag&#x65;**.**

<figure><img src="../../.gitbook/assets/image (530).png" alt=""><figcaption></figcaption></figure>

The Admin will be displayed the below SAML SSO configuration page in Cymmetri

<figure><img src="../../.gitbook/assets/image (528).png" alt=""><figcaption></figcaption></figure>

Now go back to Service Now instance and Navigate to Multi-Provider SSO > Identity Providers. Choose any existing IdP and click the Generate Metadata button. The integration automatically generates the instance's SP metadata from the system property settings.

<figure><img src="../../.gitbook/assets/image (537).png" alt=""><figcaption></figcaption></figure>

Let us come back to the SAML 2.0 settings for our managed application in Cymmetri platform and start entering the fields one by one.

SAML Type - We select the “SP\_INITIATED” from the dropdown.

<figure><img src="../../.gitbook/assets/image (531).png" alt=""><figcaption></figcaption></figure>

Since the metadata downloaded from ServiceNow does not indicate the use of a particular signature algorithm, let us simply use “RSA\_SHA256”.

<figure><img src="../../.gitbook/assets/image (532).png" alt=""><figcaption></figcaption></figure>

Further, we need to select NameID Format. Referring to the highlighted portion in the metadata downloaded from the sample application, we find only 1 supported NameID format

<figure><img src="../../.gitbook/assets/image (538).png" alt=""><figcaption></figcaption></figure>

**emailAddress:** This indicates to the managed application, that the Identity Provider (Cymmetri Platform) will be sending the end-user’s email address, and that the managed application must handle it accordingly.

We see four other NameID formats in the dropdown, let us understand them one-by-one.

<figure><img src="../../.gitbook/assets/image (533).png" alt=""><figcaption></figcaption></figure>

**NameID Formats:**

1. **unspecified:** This is a generic and default selection of NameID format, typically this would mean that the Cymmetri platform may send any user attribute, which can be selected further. The managed application must handle it accordingly. This will be used whenever some custom or unusual user attribute is to be passed to the managed application.
2. **transient:** This is used as a NameID format when we wish to indicate to the managed application, that the end-user’s details sent during the SAML 2.0 process is in fact not permanent, but may change for the period of the end-user’s identity lifecycle.&#x20;
3. **persistent:** This is used as a NameID format when we wish to indicate to the managed application, that the end-user’s details sent during the SAML 2.0 process is permanent, and will remain the same for the period of the end-user’s identity lifecycle.
4. **username:** This is used as a NameID format when we wish to indicate to the managed application, that we will be sharing the end-user’s username from Cymmetri Identity Provider to the managed application during the SAML 2.0 process.

Let us select email as the NameID format.

Let us now discuss NameID Values

There are two scenarios here -&#x20;

1. Choosing NameID format as “username” and “email” - The value of the NameID Value will not matter, the end-user’s username or email address will be shared to the managed application.
2. Choosing NameID format as “unspecified”, “transient”, and “persistent” - The value of the NameID value will allow for a particular value of the User object to be shared to the managed application.

Possible Values of NameID Value are - **email**, **mobile**, **firstName**, **lastName**, **displayName**, **loginId**.&#x20;

Let us select email as a NameID value, however, it will not affect the configuration.

<figure><img src="../../.gitbook/assets/image (535).png" alt=""><figcaption></figcaption></figure>

Let us select “Exclusive” as the Canonicalization Method. Reasons may be explained [here](https://docs.oasis-open.org/security/saml/v2.0/saml-core-2.0-os.pdf) in the SAML reference document.

<figure><img src="../../.gitbook/assets/image (536).png" alt=""><figcaption></figcaption></figure>

For configuring the “Request Issuer”, let us refer back to the downloaded metadata.xml from the Service Now application.

<figure><img src="../../.gitbook/assets/image (539).png" alt=""><figcaption></figcaption></figure>

We use the entityID from the downloaded metadata as the Entity ID

<figure><img src="../../.gitbook/assets/image (541).png" alt=""><figcaption></figcaption></figure>

Please note that the Entity ID field is how the Cymmetri platform identifies the managed application from the SAML Request sent by the managed application. Please ensure that the Entity ID is unique across the deployment.

For the Assertion Consumer Service URL, we once again refer to the downloaded XML,&#x20;

<figure><img src="../../.gitbook/assets/image (543).png" alt=""><figcaption></figcaption></figure>

Let us enter the Assertion Consumer URL as "https://dev190728.service-now.com/navpage.do"

<figure><img src="../../.gitbook/assets/image (527).png" alt=""><figcaption></figcaption></figure>

Finally, we refer to the downloaded XML one last time, for deciding upon the toggle buttons:

<figure><img src="../../.gitbook/assets/image (545).png" alt=""><figcaption></figcaption></figure>

Here we see the managed application, requires only the Assertions to be signed and not the Authentication requests, we define the toggle switches accordingly.

<figure><img src="../../.gitbook/assets/image (529).png" alt=""><figcaption></figcaption></figure>

Now go back to the main page and Download the Service provider meta data by clicking on the ellipsis in front of the record.

<figure><img src="../../.gitbook/assets/image (546).png" alt=""><figcaption></figcaption></figure>

The metadata you've downloaded will appear in a format similar to this.

<figure><img src="../../.gitbook/assets/image (286).png" alt=""><figcaption><p>Metadata </p></figcaption></figure>

Let us return back to Service Now application for completing the configuration on the Service provider side.

### _Note:_&#x20;

_Before starting the IDP Configuration the Multi Provider SSO Plugin needs to be enabled. Steps for the same are provided here:_ [_https://docs.servicenow.com/bundle/vancouver-platform-security/page/integrate/single-sign-on/task/t\_ActivateMultipleProviderSSO.html_](https://docs.servicenow.com/bundle/vancouver-platform-security/page/integrate/single-sign-on/task/t_ActivateMultipleProviderSSO.html)

_Also the plugin is activated, we need to Configure Multi-Provider SSO properties, Steps for the same are provided here:_ [_https://docs.servicenow.com/bundle/vancouver-platform-security/page/integrate/single-sign-on/task/t\_ConfigureMultiProviderSSOProps.html_](https://docs.servicenow.com/bundle/vancouver-platform-security/page/integrate/single-sign-on/task/t_ConfigureMultiProviderSSOProps.html)

_For successfully enable SSO properties you might have to configure an account recovery user, Steps for the same are provided here:_ [_https://docs.servicenow.com/bundle/vancouver-platform-security/page/integrate/single-sign-on/concept/config-acr.html_](https://docs.servicenow.com/bundle/vancouver-platform-security/page/integrate/single-sign-on/concept/config-acr.html)

_Once the above 3 steps are successfully completed we can create a new IDP_

### Create a new IDP&#x20;

Click on the New button to create a new IDP

<figure><img src="../../.gitbook/assets/image (305).png" alt=""><figcaption></figcaption></figure>

Then select SAML

<figure><img src="../../.gitbook/assets/image (306).png" alt=""><figcaption></figcaption></figure>

Then upload the metadata from the file downloaded in a previous step. and Hit Import button to store the Identity provider metadata in the application.

<figure><img src="../../.gitbook/assets/image (308).png" alt=""><figcaption></figcaption></figure>

Once imported provide the Signing/ Encryption Key Alias and Signing/ Encryption Key Password as **saml2sp** and in the Advanced Tab tick the CreateAuthnContextClass checkbox. The **Signing/ Encryption Key Alias and Signing/ Encryption Key Password** are used for encryption of data and the **CreateAuthnContextClass**  is used to tell the IDP that Service Now requires that they present a specific login mechanism such as form, Kerberos etc.&#x20;

Note: Also make sure both the logout urls present here are removed temporarily for testing purposes, else you would logout completely from ServiceNow

<figure><img src="../../.gitbook/assets/image (309).png" alt=""><figcaption></figcaption></figure>

Then enter the instance url in the SignOn configuration of the managed application on the Cymmetri portal.

<figure><img src="../../.gitbook/assets/image (310).png" alt=""><figcaption></figcaption></figure>

Click the “Save” button.

Next Create a New User in Service Now. Go to Organization->Users->New and provide the credentials of the user logged into Cymmetri as show below and Submit:

<figure><img src="../../.gitbook/assets/image (311).png" alt=""><figcaption></figcaption></figure>

#### Testing the Service Provider initiated flow

Now that both sides are configured, let us test the flow by assigning the application to the current user.

<figure><img src="../../.gitbook/assets/image (312).png" alt=""><figcaption></figcaption></figure>

Then to activate the externa IDP in Service Now we need to test the connection on the Service Now side by clicking on the Test Connection button.&#x20;

<figure><img src="../../.gitbook/assets/image (313).png" alt=""><figcaption></figcaption></figure>

Once successfully tested you should see the below screen with successful test results. Click on the Activate button to activate the IDP.

<figure><img src="../../.gitbook/assets/image (314).png" alt=""><figcaption></figcaption></figure>

Once activated Click on the  Set as Auto Redirect IdP link to automatically redirect to IDP when using a SP Initiated process

<figure><img src="../../.gitbook/assets/image (316).png" alt=""><figcaption></figcaption></figure>

Once it is enabled we can come to the currently logged in user's My Workspace-> My Access page and click on the Service Now application tile

<figure><img src="../../.gitbook/assets/image (315).png" alt=""><figcaption></figcaption></figure>

We will now be redirected to the ServiceNow home page using the logged in users crendentials as shown below:

<figure><img src="../../.gitbook/assets/image (317).png" alt=""><figcaption></figcaption></figure>

### Identity Provider Initiated Flow (IdP Initiated Flow)

The SAML 2.0 Identity Provider Initiated flow indicates that the Identity Provider (in our case, the Cymmetri platform) has started the SAML 2.0 Single SignOn process by sending an unsolicited SAML 2.0 response XML to the Cymmetri Identity platform. This is achieved by the user clicking on the managed application tile in their workspace.

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003449692/original/_F-No38I_l1Fv6B_W5-9EBWhUIA0l3Cydw.png?1649357855)

**Flow Description**

1. The user clicks on the application tile, which sends a request to the Cymmetri platform backend to initiate the SAML 2.0 SignOn process.
2. The backend validates whether the user is authorised to access the application for which the SSO request has been initiated. (by checking whether the user is assigned the application.)
3. The backend services of the Cymmetri platform generates a SAML response XML body and send it as GET request query parameter (if the protocol binding expected in the SAML request is HTTP Redirect) or as a POST request body (if the protocol binding expected in the SAML request is HTTP POST binding) to the Assertion Consumer Service URL mentioned in the SAML Request body, with the SAML Response audience as the Issuer mentioned in the SAML request body, and a field “InResponseTo” as the Request ID from the SAML request body.
4. The managed application would then validate the SAML response (and the signature, if was requested in the SAML request body).&#x20;
5. If the SAML Response body is not a valid SAML Response, then the user is redirected to the managed application’s error page.
6. If the SAML response body is a valid SAML response, then the SAML assertion is extracted to obtain the user information sent by the Cymmetri platform.
7. If the user information is not valid, for any reason, then the corresponding error is displayed to the user by redirecting the user to the managed application’s error page.
8. If all the user information is valid, the managed application initiates the user’s session in the managed application web portal, and corresponding session cookies are generated.
9. Finally, the user is redirected from the application’s Assertion Consumer Service URL to the landing page of the managed application.

### Identity Provider(IdP) Initiated Flow Configuration

The configuration parameters mentioned in the information panel below are required to configure an application for Single SignOn using the Identity provider initiated flow in the Cymmetri Identity portal.

**Prerequisites from the managed Application**

1. **Entity ID/ Request Issuer:** This is the entity id/ request issuer that would have been sent by the managed application in case this were a Service Provider initiated flow.
2. **Assertion Consumer Service URL** - This is the URL to which the SAML response must be sent by the Cymmetri Identity platform.
3. **Expected NameID Policy** - This indicates whether the managed application expects the user subject name to be sent as the **email address**, **username**, or some other unspecified value.
4. **Expected Signature Algorithm** - The expected algorithm to be used for signing the responses and assertions.

Note: Identity Provider initiated flow is a subset of the Service Provider initiated flow. Some steps are similar if you have already configured the Service Provider initiated flow.

Initially, we include a SAML service provider from the Single Sign-On section under Service Providers by selecting the "Add New" button located at the top right corner of the pag&#x65;**.**

<figure><img src="../../.gitbook/assets/image (204).png" alt=""><figcaption></figcaption></figure>

The Admin will be displayed the below SAML SSO configuration page in Cymmetri&#x20;

Let us start entering the fields one by one.

SAML Type - We select the “IDP\_INITIATED” from the dropdown.

<figure><img src="../../.gitbook/assets/image (203).png" alt=""><figcaption></figcaption></figure>

All the remaining steps for configuring IdP Initiated SAML 2.0 flow are same as shown above in the SP Initiated flow.

### Testing the Identity Provider Initiated Flow

Now that both sides are configured, let us test the flow by assigning the application to the current user.

Click on the currently logged in user's My Workspace-> My Access page and click on the Service Now application tile

<figure><img src="../../.gitbook/assets/image (315).png" alt=""><figcaption></figcaption></figure>

We will now be redirected to the ServiceNow home page using the logged in users crendentials as shown below:

<figure><img src="../../.gitbook/assets/image (317).png" alt=""><figcaption></figcaption></figure>

### Identity Provider Initiated Flow (IdP Initiated Flow)

### Possible Error Scenarios in Validation

**Scenario 1:** SAML request body does not meet the validation requirements for the SAML request.&#x20;

**Cause:** Incorrect implementation of the SAML protocol by the managed application.

**Fix:** Verify that the SAML protocol is accurately implemented by the managed application.

**Scenario 2:** SAML request body does not have the same issuer as the configuration in the Cymmetri platform.

**Cause:** Incorrect configuration of SignOn on the Cymmetri platform for the managed application.

**Fix:** Change the request Issuer in the managed application configuration on the Cymmetri platform according to the Issuer field in the SAML request.

**Scenario 3:** SAML response body does not meet the validation requirements for the SAML response.

**Cause:** Incompatible expectations of the SAML 2.0 response body between the managed application and the Cymmetri Identity platform.

**Fix:** Connect with the Cymmetri Identity platform support team.

**Scenario 4:** SAML Response assertion has the incorrect audience.

**Cause:** Incorrect configuration of the entity id/request issuer field in the Cymmetri Identity platform for the managed application.

**Fix:** Verify and change the entity id/ request issuer field in the managed application configuration on the Cymmetri platform according to the Issuer field in the SAML request.

**Scenario 5a:** User from the SAML Assertion is not valid.

**Cause:** Incorrect name ID format.

**Fix:** Verify and change the NameID format as expected by the managed application.

**Scenario 5b:** User from the SAML Assertion is not valid.

**Cause:** Incorrect user field in the assertion.

**Fix:** Verify that the right user field is selected as the “NameID Value” in the managed application configuration and Verify that the user information has the correct information as expected by the managed application in the field selected as the “NameID Value” in the managed application configuration on the Cymmetri platform.

**Scenario 5c:** User from the SAML Assertion is not valid.

**Cause:** User information is as expected but scenario 5b is not the cause.

**Fix:** Verify that the user information is present in the user database of the managed application. In case the managed application has JIT feature, ensure that the SAML attributes are correctly configured.&#x20;

### SAML Attribute Mapper&#x20;

A SAML Attribute Mapper is a component or feature in a Single Sign-On (SSO) or identity federation system that helps map user attributes between different identity providers (IdPs) and service providers (SPs) during the SAML (Security Assertion Markup Language) authentication process.

Here's how it works:

1. **Authentication**: When a user tries to access a service or application that requires authentication, they are redirected to an identity provider (IdP) for authentication. The IdP verifies the user's identity and generates a SAML assertion containing information about the user.
2. **SAML Assertion**: The SAML assertion typically contains various attributes about the user, such as their username, email address, roles, or other user-related information. These attributes are represented as name-value pairs.
3. **Attribute Mapping**: Before the SAML assertion is sent to the service provider (SP), which is the application or service the user is trying to access, there may be a need to map or transform these attributes. This is where the SAML Attribute Mapper comes into play.
   * **Attribute Transformation**: Sometimes, the IdP may use different attribute names or formats than what the SP expects. The SAML Attribute Mapper can transform the attributes in the SAML assertion to match the expectations of the SP.
   * **Filtering**: The mapper can also be used to filter or select specific attributes from the SAML assertion. For example, if the IdP provides a wide range of attributes, but the SP only needs a subset of them, the mapper can be configured to include only the required attributes in the assertion sent to the SP.
   * **Value Mapping**: It can map attribute values as well. For instance, if the IdP uses "userType=employee" and the SP expects "role=employee," the mapper can perform this value mapping.
4. **Forwarding to SP**: Once the attributes in the SAML assertion are mapped or transformed as necessary, the SAML assertion is forwarded to the service provider. The SP can then use these attributes for authorization and access control decisions.

### Configure SAML attributes

In case of default attributes, the user object already has the attributes, we just need to ensure that the right values are assigned to these attributes. In case of custom attributes, custom attributes must be added to your Cymmetri Identity platform deployment.

| **Cymmetri Attribute**            | **Default / Custom** |
| --------------------------------- | -------------------- |
| `user.eduPersonPrincipalName`     | Custom               |
| `user.eduPersonTargetedID`        | Custom               |
| `user.displayName`                | Default              |
| `user.cn`                         | Custom               |
| `user.givenName`                  | Custom               |
| `user.sn`                         | Custom               |
| `user.mail`                       | Default              |
| `user.schacHomeOrganization`      | Custom               |
| `user.schacHomeOrganizationType`  | Custom               |
| `user.schacPersonalUniqueCode`    | Custom               |
| `user.eduPersonAffiliation`       | Custom               |
| `user.eduPersonScopedAffiliation` | Custom               |
| `user.eduPersonEntitlement`       | Custom               |
| `user.eduPersonOrcid`             | Custom               |
| `user.isMemberOf`                 | Custom               |
| `user.preferredLanguage`          | Custom               |
| `user.eckid`                      | Custom               |
| `user.surfCrmId`                  | Custom               |
| `user.uid`                        | Default              |
| `user.login`                      | Default              |
| `user.firstName`                  | Default              |
| `user.lastName`                   | Default              |
| `user.country`                    | Default              |
| `user.countryCode`                | Default              |
| `user.city`                       | Default              |
| `user.mobile`                     | Default              |
| `user.address1`                   | Default              |
| `user.address2`                   | Default              |
| `user.managerId`                  | Default              |
| `user.userType`                   | Default              |
| `user.orgUnitId`                  | Default              |
| `user.employeeId`                 | Default              |
| `user.department`                 | Default              |
| `user.designation`                | Default              |
| `user.status`                     | Default              |
| `user.associatedPartner`          | Default              |
| `user.dateOfBirth`                | Default              |
| `user.landline`                   | Default              |

Let us investigate how this works out in the SAML 2.0 process and how the data is received from the Cymmetri Identity platform.

<figure><img src="../../.gitbook/assets/image (282).png" alt=""><figcaption></figcaption></figure>

Let us click on the “configure SAML attributes” link in the configuration page

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003450226/original/sbhjjgPxGfgvgbUljsZMfMik0b2D_ZXylQ.png?1649358464)

On clicking the following should pop up

<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003450251/original/jKycAxozl-VJr2u6hPkK8o4QTpuWDOpHjQ.png?1649358478" alt=""><figcaption></figcaption></figure>

Let us add an attribute mapper as per the table defined above

We have added the First Name of the user from the Cymmetri Identity Platform to the managed Application as the key “First Name”.

<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003450281/original/bklvb5IIDLHv9Ou8SNvKXZLQQaz7YrcR2g.png?1649358506" alt=""><figcaption></figcaption></figure>

\
Click on the save icon next to the delete icon (trash can icon).

\
Click on the “X” icon to close the attribute mapper.

Now once again go back to the “My Access” page and click the application tile.

Service Now can use this data for auto provisioning of users via jit provisioning provided Auto Provisioning User is enabled under the User Provisioning tab in the Identity Provider Configuration page.

<figure><img src="../../.gitbook/assets/image (320).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (319).png" alt=""><figcaption></figcaption></figure>

### Samples

#### SAML 2.0 Sample Request

<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003450344/original/DAdy3mEiROiX8U6Mg7i6qT1Ptkci7KwcIQ.png?1649358577" alt=""><figcaption></figcaption></figure>

#### SAML 2.0 Sample Response

```
<saml2p:Response xmlns:saml2p="urn:oasis:names:tc:SAML:2.0:protocol"
                 Destination="https://dev165684.service-now.com/navpage.do"
                 ID="_6db464f3-b783-4834-98ea-6ed1681dd2cd"
                 IssueInstant="2023-09-26T10:19:01.472Z"
                 Version="2.0"
                 >
    <saml2:Issuer xmlns:saml2="urn:oasis:names:tc:SAML:2.0:assertion">ccaa</saml2:Issuer>
    <saml2p:Status>
        <saml2p:StatusCode Value="urn:oasis:names:tc:SAML:2.0:status:Success" />
    </saml2p:Status>
    <saml2:Assertion xmlns:saml2="urn:oasis:names:tc:SAML:2.0:assertion"
                     xmlns:xs="http://www.w3.org/2001/XMLSchema"
                     ID="_e4baa225-cd79-4ac2-93b3-0a5ab7ef2f87"
                     IssueInstant="2023-09-26T10:19:01.472Z"
                     Version="2.0"
                     >
        <saml2:Issuer>ccaa</saml2:Issuer>
        <ds:Signature xmlns:ds="http://www.w3.org/2000/09/xmldsig#">
            <ds:SignedInfo>
                <ds:CanonicalizationMethod Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#" />
                <ds:SignatureMethod Algorithm="http://www.w3.org/2001/04/xmldsig-more#rsa-sha256" />
                <ds:Reference URI="#_e4baa225-cd79-4ac2-93b3-0a5ab7ef2f87">
                    <ds:Transforms>
                        <ds:Transform Algorithm="http://www.w3.org/2000/09/xmldsig#enveloped-signature" />
                        <ds:Transform Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#">
                            <ec:InclusiveNamespaces xmlns:ec="http://www.w3.org/2001/10/xml-exc-c14n#"
                                                    PrefixList="xs"
                                                    />
                        </ds:Transform>
                    </ds:Transforms>
                    <ds:DigestMethod Algorithm="http://www.w3.org/2001/04/xmlenc#sha256" />
                    <ds:DigestValue>4BaEkbuyzytz0XkXo19cBeLjGnYrTOvPhxfv3NWyidc=</ds:DigestValue>
                </ds:Reference>
            </ds:SignedInfo>
            <ds:SignatureValue>vRw1lhio5G38L/inuAp9l9yjekbCCM4BduLykL7vg4wijlHmbrSMiNJNuqOu8vO79Aqruj6GBafGRD6Slqrco5vScsWbfH5LiHz5UejAh2sGsqbQHapYFPlZJ6ErauwFxbzGN7od5CYlZUgDPUdO1dF2jiwoYeqhs+aQOISsyoq9pcQ2yl35wmaUy6C388a+m54OzygQhwsQdxEeA1OqLDtAw3ulTxbKsjRw1hAa7zv4JKKO10HirrWwWXDe3dSsh2Z3um0sF6TxWjV5wKXKflXz1alNPcNBONTjTWOfwKD/a+agZITQ8jGJAo6vZXfF3bI7N0uo3dWF3ogK2jzpjg==</ds:SignatureValue>
        </ds:Signature>
        <saml2:Subject>
            <saml2:NameID Format="urn:oasis:names:tc:SAML:1.1:nameid-format:emailAddress">Ak@mail.com</saml2:NameID>
            <saml2:SubjectConfirmation Method="urn:oasis:names:tc:SAML:2.0:cm:bearer">
                <saml2:SubjectConfirmationData NotOnOrAfter="2023-09-26T18:19:01.472Z"
                                               Recipient="https://dev165684.service-now.com/navpage.do"
                                               />
            </saml2:SubjectConfirmation>
        </saml2:Subject>
        <saml2:Conditions NotBefore="2023-09-26T10:16:01.472Z"
                          NotOnOrAfter="2023-09-26T10:22:01.472Z"
                          >
            <saml2:AudienceRestriction>
                <saml2:Audience>https://dev165684.service-now.com</saml2:Audience>
            </saml2:AudienceRestriction>
        </saml2:Conditions>
        <saml2:AuthnStatement AuthnInstant="2023-09-26T10:19:01.472Z"
                              SessionIndex="_e4baa225-cd79-4ac2-93b3-0a5ab7ef2f87"
                              >
            <saml2:AuthnContext>
                <saml2:AuthnContextClassRef>urn:oasis:names:tc:SAML:2.0:ac:classes:unspecified</saml2:AuthnContextClassRef>
            </saml2:AuthnContext>
        </saml2:AuthnStatement>
        <saml2:AttributeStatement>
            <saml2:Attribute Name="User Name"
                             NameFormat="urn:oasis:names:tc:SAML:2.0:attrname-format:uri"
                             >
                <saml2:AttributeValue xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
                                      xsi:type="xs:string"
                                      >Ak@123</saml2:AttributeValue>
            </saml2:Attribute>
            <saml2:Attribute Name="email"
                             NameFormat="urn:oasis:names:tc:SAML:2.0:attrname-format:uri"
                             >
                <saml2:AttributeValue xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
                                      xsi:type="xs:string"
                                      >Ak@mail.com</saml2:AttributeValue>
            </saml2:Attribute>
            <saml2:Attribute Name="firstName"
                             NameFormat="urn:oasis:names:tc:SAML:2.0:attrname-format:uri"
                             >
                <saml2:AttributeValue xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
                                      xsi:type="xs:string"
                                      >Akash</saml2:AttributeValue>
            </saml2:Attribute>
            <saml2:Attribute Name="lastName"
                             NameFormat="urn:oasis:names:tc:SAML:2.0:attrname-format:uri"
                             >
                <saml2:AttributeValue xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
                                      xsi:type="xs:string"
                                      >Patil</saml2:AttributeValue>
            </saml2:Attribute>
        </saml2:AttributeStatement>
    </saml2:Assertion>
</saml2p:Response>
```
