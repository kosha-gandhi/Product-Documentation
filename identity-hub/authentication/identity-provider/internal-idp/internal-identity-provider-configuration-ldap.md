# Internal Identity Provider Configuration: LDAP

Lightweight Directory Access Protocol (LDAP) serves as an important Identity Provider (IDP) in enterprise environments. It authenticates and authorizes users, facilitating seamless access to resources. LDAP is commonly used as a directory service for managing user identities and authentication information within an organization.

LDAP can be utilized in Cymmetri as an Identity Provider (IDP), leveraging existing user accounts to access Cymmetri, as the platform supports the LDAP protocol.

For configuring LDAP as an Identity Provider one of the primary services needed is the **Adapter Service.**

### The Adapter Service

The Adapter Service or Auth Adapter Service is exposed as a rest service that runs on HTTPS acts as an adapter to facilitate authentication using the LDAP protocol which is often employed for authentication purposes in various systems and every adapter service instance is called by the **secret** generated while installation/configuration of adapter service.

The rest endpoints are called by cymmetri-cloud AuthenticationService to connect to On-Prem AD/Ldap or cloud AD/Ldap. The AdaptorService is used to test connections, authenticate, change, and reset the password of a user.

### Configuration

For configuring Active Directory as an internal IDP  navigate to **Authentication -> Identity Provider -> Internal IDP.** Here you may either configure the already created **LDAP Authentication** instance or **+Add New**

<figure><img src="../../../../.gitbook/assets/image (186).png" alt=""><figcaption></figcaption></figure>

In either case, a screen opens where you need to provide the below-mentioned details

* **Name**: LDAP Authentication
* **IDP Type**: Open LDAP
* **Description:** A general description of the IDP type
* **Status:** Active
* **Adapter Service Domain:** Location (IP) of the server on which the Adapter Service is deployed
* **Adapter Service Secret:** The **secret** generated while installing/configuring of adapter service
* **Base DN:** LDAP root domain name
*   **Search Scope:** A search scope for locating users in LDAP

    <figure><img src="../../../../.gitbook/assets/image (187).png" alt=""><figcaption></figcaption></figure>

Once all the details are entered Save the changes and Test the Connection using the **Test Connection** button.

For enabling Open LDAP to be used as an IDP for a specific set of users an Authentication Rule needs to be configured. [Here ](../../authentication-rules.md)you can see the steps on how to configure Authentication Rules.

Once the rule is configured, whenever a user matches the rule conditions, their credentials are verified against those stored in LDAP. Upon successful verification, the user is granted access to log in to Cymmetri.
