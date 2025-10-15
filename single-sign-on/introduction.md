# Introduction

Cymmetri's Single Sign-On (SSO) module is designed to simplify user authentication within the Cymmetri platform's web portal. With SSO, end-users authenticate just once, gaining seamless access to all their assigned applications without the hassle of repeated logins.&#x20;

This article provides step-by-step guidance on configuring applications for SSO within your Cymmetri platform.

**Note:** Before proceeding with the configuration, ensure that the Single Sign-On Module is enabled for your tenant to activate and utilize SSO effectively.

## **Supported Single Sign-On Mechanisms:**

**1. SAML 2.0**_**:**_ SAML 2.0 (Security Assertion Markup Language) serves as a primary mechanism for web applications to exchange messages, facilitating Single Sign-On for end-users.

**2. OpenID Connect**_**:**_ Derived from the OpenID family of SSO mechanisms, OpenID Connect offers versatile SSO capabilities across a wide range of application types, including web, mobile native, and desktop-based applications. It is therefore more versatile than SAML 2.0, and  particularly well-suited for mobile applications and social logins.

**Note:** For either SAML 2.0 or OpenID Connect to function, the managed application must support the corresponding mechanism.

**3.** **REST API-Based SSO:** While SAML 2.0 and OpenID Connect adhere to established standards, certain legacy applications within your organization may face integration challenges with these protocols. To address this, we have introduced Custom API-Based SSO as an alternative SSO mechanism. This involves making specific code modifications to the managed application, as elaborated in the following section.

**Note:** While the Cymmetri Identity platform supports Custom API-Based SSO, we strongly recommend transitioning to the aforementioned SAML 2.0 and OpenID Connect mechanisms for enhanced security and compatibility.

### Configuring Applications for Single SignOn

To allow your end-users to access applications managed by your Cymmetri Identity platform deployment, the applications must be configured for Single SignOn, and then assigned the application.

To enable end-users to access applications managed through your Cymmetri platform, applications must configure Single Sign-On for the desired applicationsa

#### Redirect to Applications without Single SignOn

While it is not recommended for obvious reasons, as an administrator you may configure an application to be used simply for provisioning and redirection, without performing Single SignOn.&#x20;

Note: The following section is to be used for configure only applications for which you do not need to perform Single SignOn. In case you need to configure any of the following Single SignOn mechanisms, you may skip this section and refer to the corresponding configuration in your chosen method of Single SignOn.

_**Configuring the Application URL**_

For configuring an application to simply redirect the enduser to the landing page of the managed application -&#x20;

<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003447794/original/_gl6lm9AEyk1qmbJL6IsD5wdZY-i38V3pA.png?1649355214" alt=""><figcaption></figcaption></figure>

Once in the applications menu, click on the application tile for which you need to configure the landing page URL and then on the left side menu, select the SignOn menu item.

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003447798/original/BZ4tNaZ7G4oLqN3FRqiCf5O_Qy2JUMOeDg.png?1649355242)

\


Toggle the “Enable Single Sign-On (SSO)” switch to open the corresponding configuration options.

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003447800/original/ZNheWnUvVQJYSWYbWskhqFXpi4Xo3zVZqA.png?1649355252)

Enter the landing page URL in the “Application URL” text box and click the adjoining “Save” button.

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003447813/original/Dzyieg7WL6IYTwZArS-uNof4_L5VtaYrnA.png?1649355263)

The popup indicating “SSO Updated Successfully” will indicate that the Application URL has been configured successfully for your application.

**Conclusion**

Assigning the application to an end user will show an application tile as shown below:

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003447820/original/OIqaFpQbhsnr6neUsA90JtrfG8paDARLgg.png?1649355279)

Clicking on the application tile, will redirect the user to the assigned landing page URL.
