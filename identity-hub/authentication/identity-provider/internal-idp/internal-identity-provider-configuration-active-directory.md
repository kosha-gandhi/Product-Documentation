# Internal Identity Provider Configuration: Active Directory

Active Directory (AD) is a robust Identity Provider (IDP) in enterprise environments. It authenticates and authorizes users, facilitating seamless access to resources. AD centralizes user management, streamlining security protocols and ensuring efficient user provisioning.

Active Directory can be utilized in Cymmetri as an Identity Provider (IDP), leveraging existing AD user accounts to access Cymmetri, as the platform supports the LDAP protocol.

For configuring AD as an Identity Provider, the primary service needed is the **Adapter Service.**

### The Adapter Service

The Adapter Service or Auth Adapter Service is exposed as a rest service that runs on HTTPS and acts as an adapter to facilitate authentication using the LDAP protocol which is often employed for authentication purposes in various systems and every adapter service instance is called by the **secret** generated while installation/configuration of adapter service.

The rest endpoints are called by cymmetri-cloud AuthenticationService to connect to On-Prem AD/Ldap or cloud AD/Ldap. The AdaptorService is used to test connections, authenticate, change, and reset the password of a user.

### Configuration

For configuring Active Directory as an internal IDP  navigate to **Authentication -> Identity Provider -> Internal IDP.** Here you may either configure the already created **AD Authentication** instance or **+Add New.**

<figure><img src="../../../../.gitbook/assets/image (581).png" alt=""><figcaption></figcaption></figure>

In either case, a screen opens where you need to provide the below-mentioned details.

* **Name**: AD Authentication
* **IDP Type**: Active Directory
* **Description:** A general description of the IDP type
* **Status:** Active
* **Adapter Service Domain:** Location (IP) of the server on which the Adapter Service is deployed
* **Adapter Service Secret:** The **secret** generated while installing/configuring of adapter service
* **Base DN:** Active Directory root domain name
*   **Search Scope:** A search scope for locating users in Active Directory

    <figure><img src="../../../../.gitbook/assets/image (582).png" alt=""><figcaption></figcaption></figure>

Once all the details are entered Save the changes and Test the Connection using the **Test Connection** button.

For enabling Active Directory to be used as an IDP for a specific set of users an Authentication Rule needs to be configured. [Here ](../../authentication-rules.md)you can see the steps on how to configure Authentication Rules.

Once the rule is configured, whenever a user matches the rule conditions, their credentials are verified against those stored in the Active Directory. Upon successful verification, the user is granted access to log in to Cymmetri.
