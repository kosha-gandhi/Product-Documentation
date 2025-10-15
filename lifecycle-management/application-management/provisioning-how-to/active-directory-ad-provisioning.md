# Active Directory (AD) Provisioning

This document provides a formal, step-by-step guide to configuring an AD integration with the Cymmetri platform. This integration allows Cymmetri to act as a central identity store, managing users and their attributes within the AD environment.

Before beginning the configuration, ensure you have the following:

* Domain Administrator Credentials: A username and password for a AD account with full administrative privileges.
* Domain & Controller Details: The Domain Name and the IP address or hostname of the AD domain controller.
* SSL/TLS Certificates: For secure communication via port 636, the Certificate Authority (CA) certificate must be exported from the AD server and imported into the Cymmetri connector server. This ensures the communication channel is trusted and encrypted. Refer the link below for more details: [ https://www.manageengine.com/products/active-directory-audit/kb/how-to/how-to-install-ssl-certificates-in-active-directory.html](https://www.manageengine.com/products/active-directory-audit/kb/how-to/how-to-install-ssl-certificates-in-active-directory.html)
* Network Access: Ensure that necessary ports (especially 636 for secure LDAPS communication) are open and accessible between the Cymmetri connector server and the AD domain controller.

#### Configuration Steps

**Step 1:** Configure your Active Directory Certificate and export it to Connector Server

Exporting your Active Directory certificate to the Connector Server is a necessary and crucial step. This ensures that the Active Directory and Cymmetri Identity Server can communicate over LDAPS (LDAP over SSL). For this to happen, LDAPS requires a properly formatted certificate installed in your Active Directory Domain Controllers. Please refer to this link and follow the same steps: [https://www.manageengine.com/products/active-directory-audit/kb/how-to/how-to-install-ssl-certificates-in-active-directory.html](https://www.manageengine.com/products/active-directory-audit/kb/how-to/how-to-install-ssl-certificates-in-active-directory.html)

Once the certificate has been imported per the above instructions, you must restart the application to apply the changes made.



**Step 2: Create the AD Application in Cymmetri**

1. Navigate to the Identity Hub and select Application.

<figure><img src="../../../.gitbook/assets/unknown (8).png" alt=""><figcaption></figcaption></figure>

2. Click Create Application.
3. Search for "Active Directory" and select the appropriate application type.
4. Name the application "Simple AD" to easily identify it within Cymmetri.

<figure><img src="../../../.gitbook/assets/unknown (9).png" alt=""><figcaption></figcaption></figure>

**Step 3: Create a Policy Map**

The policy map defines the attribute mapping between Cymmetri and AD. This is crucial for synchronizing user data correctly.

1. Go to the Policy Attribute section.
2. Review the pre-filled, standard attribute mappings (e.g., sAMAccountName to login, givenName to firstName, mail to email).

<figure><img src="../../../.gitbook/assets/unknown (11).png" alt=""><figcaption></figcaption></figure>

3. Add any new or custom attributes by clicking Add new, entering the attribute name and description, and saving.

<figure><img src="../../../.gitbook/assets/unknown (10).png" alt=""><figcaption></figcaption></figure>

**Step 4: Configure User & Server Settings**

This two-part step establishes the connection parameters and user search criteria.

User Configuration:

* Principal & Principal Password: Enter the credentials of the domain administrator account. This account is used by Cymmetri to connect to AD.

<figure><img src="../../../.gitbook/assets/unknown (12).png" alt=""><figcaption><p>principal</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/unknown (13).png" alt=""><figcaption><p>(principal password)</p></figcaption></figure>

* Server Hostname: The IP address or hostname of the AD domain controller.

<figure><img src="../../../.gitbook/assets/unknown (15).png" alt=""><figcaption></figcaption></figure>

* User Entry Searches & Base Contexts: Define the LDAP search queries and organizational units (OUs) that Cymmetri will use to find users and groups within AD.

<figure><img src="../../../.gitbook/assets/unknown (16).png" alt=""><figcaption><p>user search entries</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/unknown (17).png" alt=""><figcaption><p>Base Contexts</p></figcaption></figure>

Click Save Configuration and then Test Configuration to verify a successful connection.

<figure><img src="../../../.gitbook/assets/unknown (18).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/unknown (19).png" alt=""><figcaption></figcaption></figure>

Server Configuration:

* Server Hostname: The hostname of the Cymmetri connector server.

<figure><img src="../../../.gitbook/assets/unknown (20).png" alt=""><figcaption></figcaption></figure>

* Server Password: The password for the connector server.

<figure><img src="../../../.gitbook/assets/unknown (21).png" alt=""><figcaption></figcaption></figure>

* Server Port: The port number for communication (e.g., 636 for secure LDAPS).

<figure><img src="../../../.gitbook/assets/unknown (22).png" alt=""><figcaption></figcaption></figure>

* Connector Bundle Name & Version: The name and version of the Cymmetri connector bundle, which facilitates communication with AD.

<figure><img src="../../../.gitbook/assets/unknown (24).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/unknown (23).png" alt=""><figcaption></figcaption></figure>

* Click Save Configuration, then Test Configuration.

<figure><img src="../../../.gitbook/assets/unknown (25).png" alt=""><figcaption></figcaption></figure>

**Step 5: Perform a Reconciliation (Push)**

A Push Reconciliation is the process of synchronizing user data from Cymmetri to the AD target system.

1. Navigate to Reconciliation.
2. Select the Push option.
3. Click Add New to create a new push reconciliation job.

<figure><img src="../../../.gitbook/assets/unknown (28).png" alt=""><figcaption></figcaption></figure>

4. Configure the job settings and execute it.

<figure><img src="../../../.gitbook/assets/unknown (27).png" alt=""><figcaption></figcaption></figure>

5. Monitor the job status by navigating to Recon History.

<figure><img src="../../../.gitbook/assets/unknown (29).png" alt=""><figcaption></figcaption></figure>

**Step 6: Verify Reconciliation in AD**

To confirm that the push reconciliation was successful, verify the user data directly within the AD target system.

1. Use Remote Desktop Protocol (RDP) to connect to the AD server.

<figure><img src="../../../.gitbook/assets/unknown (30).png" alt=""><figcaption></figcaption></figure>

2. Enter the computer credentials (IP address and password) to connect.

<figure><img src="../../../.gitbook/assets/unknown (31).png" alt=""><figcaption></figcaption></figure>

3. Once logged in, open the Active Directory management console.

<figure><img src="../../../.gitbook/assets/unknown (32).png" alt=""><figcaption></figcaption></figure>

4. Right-click on the domain and use the Find function to search for the user who was pushed from Cymmetri. If the user appears with the correct attributes, the reconciliation was successful.

<figure><img src="../../../.gitbook/assets/unknown (33).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/unknown (35).png" alt=""><figcaption></figcaption></figure>
