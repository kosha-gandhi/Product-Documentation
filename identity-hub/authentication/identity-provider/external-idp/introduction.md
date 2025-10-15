# Introduction

Cymmetri's External Identity Provider (IdP) feature allows you to authenticate user identities using different IdPs for various user types. This flexible configuration enables you to streamline access for both internal employees and external users, such as consultants, vendors, and their employees. In this documentation, we will guide you through the process of configuring an External IdP within Cymmetri's identity and access management system.

For internal employees, you can configure Cymmetri's Internal IdP mechanisms like Active Directory or LDAP. This allows seamless authentication for your organization's employees.

Whereas external users, such as consultants, vendors, and their employees, can be verified using popular External IdPs like Google, Azure, Salesforce, or any other supported IdP. This approach simplifies access for external parties while maintaining security and control.

<figure><img src="../../../../.gitbook/assets/image (490).png" alt=""><figcaption></figcaption></figure>

### Configuring External Identity Providers

To configure an External IdP in Cymmetri, the administrator needs to provide the following information:

1. **Name**: A descriptive name for the External IdP configuration.
2. **IDP Type**: The type or provider of the IdP (e.g., Google, Azure, Salesforce).
3. **Entity ID**: The unique identifier for the IdP entity.
4. **SSO Service URL**: The URL where Single Sign-On (SSO) requests should be sent.
5. **Destination**: The location where authentication responses should be directed.
6. **Protocol Binding**: The protocol used for communication with the IdP (e.g., HTTP Post, HTTP Redirect).
7. **Name ID Policy and Value**: This policy defines the format and content of the identifier that represents the authenticated user. For example:
   * **Policy**: email
   * **Value**: email
8. **Certificate**: The certificate used for secure communication between Cymmetri and the External IdP.

In the upcoming sections we will learn step-by-step implementation of the various External IDP mechanisms:

#### Google:

Google serves as a robust external Identity Provider (IDP) through its Identity Platform. Leveraging various authentication mechanisms, it facilitates secure user authentication for Cymmetri. This allows users to sign in with their Google credentials, ensuring a seamless and familiar login experience. Google's IDP mechanism is adopted for its reliability and user-friendly authentication processes, thus making it a preferred choice for integration into Cymmetri as an External IDP.

#### Azure Active Directory (Azure AD):

Azure AD serves as a robust external IDP, facilitating secure access into Cymmetri. Employing industry standards like OAuth 2.0 and SAML, it enables Single Sign-On (SSO) and multi-factor authentication. Azure AD seamlessly integrates with Cymmetri providing easy identity management and ensuring compliance with modern security standards.

#### Salesforce:

Salesforce as an external Identity Provider (IDP) offers robust authentication and access control solutions. Utilizing industry-standard protocols like SAML and OAuth, Salesforce IDP ensures secure Single Sign-On (SSO) experiences.&#x20;

Configuring External Identity Providers in Cymmetri gives you the flexibility to authenticate user identities using different IdPs tailored to specific user types. Whether it's for internal employees or external collaborators, Cymmetri's External IdP feature ensures secure and convenient access to your organization's resources.
