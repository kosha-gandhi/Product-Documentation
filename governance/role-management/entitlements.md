# Entitlements

Entitlements refer to the permissions or rights granted to a user or group to access specific resources or perform certain actions within a system. These entitlements are typically defined based on the user's role, job function, or other relevant attributes associated with the user.&#x20;

## Key elements about entitlements

**Authorization**: Entitlements are closely tied to authorization, which is the process of determining whether a user is allowed to perform a specific action.\
**Access Control:** Entitlements are a fundamental component of access control, ensuring that only authorized individuals can access sensitive information or systems.\
**Role-Based Access Control (RBAC):** Entitlements are often assigned based on a user's role within an organization, making it easier to manage access permissions for large groups of users.\
**Least Privilege Principle:** The principle of least privilege states that users should be granted only the minimum entitlements necessary to perform their job duties, reducing the risk of unauthorized access.\
**Entitlement Management:** This refers to the process of managing and controlling entitlements throughout their lifecycle, including granting, revoking, and auditing.

### Examples of entitlements

* A sales representative might have entitlement to access customer data and place orders.
* A system administrator might have entitlement to modify system settings and troubleshoot issues.
* A guest user might have entitlement to view public content on a website but not to make purchases.
* By effectively managing entitlements, organizations can improve security, compliance, and efficiency.

### Provisioning of Entitlements

In Cymmetri, the ability to provide an object (such as a user or group) access to a resource (application, group, role, permission, privileged system) is called provisioning of entitlements.

&#x20;Broadly classified, the following are the entitlements possible for access based provisioning:

* Business Role
* Group
* Application
* Application Role
* Privileged System&#x20;
* Cymmetri Role

&#x20;In Cymmetri the above mentioned entitlements are provisioned to either:

* Cymmetri Users
* Cymmetri Groups

### Discover Entitlements

Cymmetri provides a framework for identifying entitlements within various target applications. The most common of these are accounts or user objects in the target system. The other elements that can be detected are group or group objects and roles.

For account discovery, various Cymmetri connectors provide ready made detection capability. The most common among them are-

1. [Active Directory](https://help.cymmetri.io/lifecycle-management/application-management/provisioning-how-to/active-directory-ad-provisioning#pull-reconciliation)
2. Azure AD
3. REST API Connector
4. AMAYA Connector
5. SAP HANA Connector
6. SCIM Connectors

Apart from the standard reconciliation approach, Cymmetri also provides a [360 degree reconciliation](https://help.cymmetri.io/lifecycle-management/application-management/getting-started/360-degree-recon) to discover identities / accounts which do not co-relate with Cymmetri records or vice-versa.&#x20;

After discovery of identities, Cymmetri can be configured to perform the corresponding action such as-

1. Assign or Link the Cymmetri user and Target system account
2. Unassign or Unlink the Cymmetri and Target system account

The possible scenarios for identity state can be referred on the [conditions](https://help.cymmetri.io/lifecycle-management/application-management/reconciliation-how-to/configuring-reconciliation-process#conditions-explained) which are in turn based on the [supported operations](../../lifecycle-management/application-management/provisioning-how-to/supported-provisioning-operations.md).&#x20;



### Role Definitions

Cymmetri has ability to manage Business and IT roles through its interface.&#x20;

The Business Roles can be defined as part of the Cymmetri RBAC Master and SoD policies. Similarly, the Application roles or IT roles can be defined at each application as its own master. Generally, the application roles are maintained at application side and Cymmetri keeps a reference for the target role entitlement.&#x20;

#### Role Update

Cymmetri allows direct syncing with target system to fetch the role master. However, in case the target system does not support APIs for role management, the roles can be added or modified based on bulk import or manually adding or updating in Cymmetri.&#x20;

#### Audit of Change History

Every role definition is saved in the Cymmetri audit log. Changes to the definition are audited and previous role configuration can be restored as needed.&#x20;

