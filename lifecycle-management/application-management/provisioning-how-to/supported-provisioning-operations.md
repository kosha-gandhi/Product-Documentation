# Supported Provisioning Operations

Cymmetri provides a robust suite of provisioning operations that enable seamless identity and access management across various applications. Below is a detailed overview of the provisioning operations supported by Cymmetri.

**1. Test Operation**

* **Purpose**: The Test Operation is used to validate the connectivity and configuration settings between Cymmetri and the target application or directory service. This operation ensures that all necessary parameters, such as API endpoints, credentials, and schema mappings, are correctly configured.
* **Usage Scenario**: Before initiating any provisioning tasks, administrators can use the Test Operation to verify that the integration between Cymmetri and the target system is functioning as expected.

**2. Sync Operation**

* **Purpose**: The Sync Operation synchronizes user and group data between Cymmetri and the connected applications. This operation ensures that the identity information in Cymmetri is in sync with the data in external systems.
* **Usage Scenario**: The Sync Operation is typically scheduled to run at regular intervals or triggered manually to ensure that changes in the external system (e.g., new users, updated roles) are reflected in Cymmetri.

**3. Search Operation**

* **Purpose**: The Search Operation allows administrators to query the target application or directory for specific users or groups. This operation is essential for identifying and managing specific identities in the external system.
* **Usage Scenario**: Administrators can use the Search Operation to find users based on attributes such as username, email, or group membership, facilitating targeted management tasks like updates or deletions.

**4. Create Operation**

* **Purpose**: The Create Operation is used to provision new user accounts or groups in the target application or directory based on the identity data maintained in Cymmetri.
* **Usage Scenario**: When a new employee joins an organization, the Create Operation can be triggered to automatically provision their account in various applications, ensuring immediate access to necessary resources.

**5. Update Operation**

* **Purpose**: The Update Operation allows administrators to modify existing user or group attributes in the target system. This operation is crucial for maintaining accurate and up-to-date identity information across systems.
* **Usage Scenario**: If an employee's role changes, the Update Operation can be used to modify their access privileges or update their profile information in connected applications.

**6. Delete Operation**

* **Purpose**: The Delete Operation is used to de-provision user accounts or groups from the target application or directory. This operation is essential for removing access when users leave the organization or no longer require certain resources.
* **Usage Scenario**: Upon the termination of an employee, the Delete Operation can be triggered to remove their accounts from all connected applications, ensuring security and compliance.

**7. Role Assign Operation**

* **Purpose**: The Role Assign Operation assigns specific roles to users in the target system, granting them access to particular resources or permissions.
* **Usage Scenario**: When an employee is promoted to a managerial position, the Role Assign Operation can be used to grant them additional access rights aligned with their new responsibilities.

**8. Role Unassign Operation**

* **Purpose**: The Role Unassign Operation removes previously assigned roles from users, revoking their access to certain resources or permissions.
* **Usage Scenario**: If an employee is reassigned to a different department, the Role Unassign Operation can be utilized to revoke roles that are no longer relevant to their new position.
