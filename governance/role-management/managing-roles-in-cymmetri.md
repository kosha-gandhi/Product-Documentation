---
description: >-
  Admin guide to Version Management of Role Definitions with Role Revert
  Capabilities
noIndex: true
---

# Managing Roles in Cymmetri

### Admin Manual: Version Management of Role Definitions with Role Revert Capabilities in Cymmetri IGA

## Overview

This document provides detailed instructions on how administrators can manage role definitions and maintain a version history in Cymmetri Identity Governance and Administration (IGA). The solution supports full versioning of roles and allows roles to be reverted to previous states while maintaining control over target system configurations. When a role is rolled back, the system also ensures that the rollback applies to all target systems where the role has been assigned or deployed.

## Features

* **Role Versioning**: All modifications to roles are tracked and stored as separate versions.
* **Target System Rollback**: When a role is rolled back, the target systems where the role has been assigned will also revert to the previous configuration.
* **Audit Trail**: Administrators can view the complete history of changes made to any role.
* **Rollback Functionality**: Ability to revert a role and its assignments to any previous version.
* **Controlled Access**: Only authorized administrators can manage role versions and apply rollbacks.

### Prerequisites

* Administrator-level access to Cymmetri IGA.
* Ensure roles and permissions are configured to allow role version management and rollback capabilities.
* Target systems should be integrated with Cymmetri IGA and configured for automatic updates when roles are reverted.

#### 1. Accessing the Role Management Module

1. **Login to Cymmetri IGA** using your administrator credentials.
2. Navigate to **Identity Governance**.
3. Click on **Role Management**.

#### 2. Viewing Role Version History

1. In the **Role Management** module, search for the specific role whose version history you want to view.
2. Select the role from the list.
3. On the role details page, click on the **History/Versioning** tab.
4. A list of all previous versions will be displayed, along with the following information:
   * Version Number
   * Date of Modification
   * Modified by (Administrator’s name)
   * Description of changes made

#### 3. Comparing Role Versions

1. To compare two versions of a role:
   * In the **History/Versioning** tab, select the two versions you want to compare by checking the boxes next to them.
   * Click the **Compare** button.
2. A side-by-side comparison will be displayed showing the differences in permissions, attributes, and other relevant configurations.

#### 4. Rolling Back to a Previous Version and Target System Revert

1. In the **Role Management** module, select the role you want to roll back.
2. Go to the **History/Versioning** tab and locate the version to which you want to revert.
3. Click the **Rollback** button next to the desired version.
4. A confirmation dialog will appear, detailing the rollback process. Confirm your action by clicking **Yes**.
   * **Role Revert on Target Systems**: When rolling back a role, Cymmetri IGA will automatically push the changes to the target systems where this role has been deployed, ensuring the role reversion is applied across all systems where the role is in use.
5. The role will now be reverted to the selected version, and a new version will be created documenting the rollback action. The target systems will reflect the same version.
6. The system will generate a notification once the rollback is complete and applied to all integrated target systems.

#### 5. Audit and Reporting

1. To view a complete audit log of all role modifications and reverts:
   * Navigate to the **Audit Reports** section from the dashboard.
   * Select **Role Change History** or **Target System Rollback Logs**.
2. Filter the report based on role name, date, or administrator.
3. The report can be exported in PDF or Excel format for compliance purposes.

#### 6. Permissions Management for Role Versioning and Rollback

1. Only authorized administrators can manage and roll back role versions and apply the changes to target systems. To assign or revoke this permission:
   * Navigate to **Configurations** → **Admins**.
   * Select the **Domain Admin** role or click on Add button to search for a user to assign the Domain Admin role.

#### 7. Notifications and Monitoring

When a role version is rolled back and applied to target systems, Cymmetri IGA will trigger notifications to relevant stakeholders and system owners:

1. Navigate to **Notification Settings** under **Configurations**.
2. Enable the **Role Version Rollback and Target System Revert Notification** and configure the recipient list.
3. Customize the email template if required.
4. **Real-Time Monitoring**: Use the **Monitoring Dashboard** to track the status of role rollbacks and ensure that all target systems have received the updated configurations.

#### 8. Best Practices

* **Regular Audits**: Conduct regular audits of role definitions and their versions to ensure compliance and avoid unauthorized changes.
* **Testing Before Rollback**: Before rolling back a critical role in a production environment, it’s advisable to test the rollback in a staging environment.
* **Confirm Target System Updates**: After a rollback, verify that all target systems reflect the correct version of the role.

### Troubleshooting

* **Unable to Roll Back**: Ensure that you have the required permissions to perform a rollback and that the selected version is valid.
* **Target Systems Not Updated**: If the role reversion has not propagated to the target systems, check the integration settings for those systems and confirm that the connection with Cymmetri IGA is active.
* **Audit Log Not Displaying Changes**: If the audit log doesn’t display recent changes, verify that role versioning is enabled in system settings.

### Conclusion

Cymmetri IGA's version management feature allows for seamless role reversion, ensuring that not only are previous versions of roles maintained, but any rollbacks are also applied across all target systems. By following this admin manual, administrators can effectively manage role versions and ensure compliance, security, and consistency across their identity governance landscape.
