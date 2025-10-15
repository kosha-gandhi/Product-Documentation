# Teams Config

The Teams Config feature is designed for Reporting Managers, providing them with controlled access based on specific conditions to perform various actions for their team members. Based on different conditions like Country, Department, Designation, Login Pattern and UserType, multiple such configurations can be created in different combinations and different sets of permissions.

### Permissions Overview

Administrators can grant the following permissions to Reporting Managers, providing a granular and secure way to delegate administrative tasks:

* Archived User Permissions
  * Archived User: Allows the manager to view archived users from their team.
* Suspend User Permissions
  * Suspend User View: Enables the manager to view suspended users from their team.
  * Suspend User Resume: Allows the manager to resume suspended users from their team.
  * Suspend User Delete: Permits the manager to delete suspended users from their team.
* User Permissions
  * Create User: Enables the manager to create new users.
  * Update User: Allows the manager to update user information.
  * User Info: (Enabled By Default) Provides access to view detailed user information.
  * User Application View: Allows the manager to view applications assigned to team members.
  * Assign Application: Permits the manager to assign applications to team members.
  * Assign Role: Enables the manager to assign roles to team members.
  * Unassign Application: Allows the manager to unassign applications from team members.
  * Unassign Role: Permits the manager to unassign roles from team members.
  * Menu Action: Grants access to context menu actions.
  * Assign Group: Enables the manager to assign user groups.
  * Unassign Group: Permits the manager to unassign user groups.

<figure><img src="../.gitbook/assets/image (462).png" alt=""><figcaption></figcaption></figure>

Manager Application

This feature operates on a principle of delegated but restricted access. When the Manager Application setting is enabled, the system establishes a direct link between the manager's own application entitlements and their delegation rights.

Manager's Assignment Scope: A manager can only assign applications to their direct reports if they are already assigned that same application. This ensures that managers can only provision access to resources for which they have a demonstrated need and an established level of authority.

User's Request Scope: Correspondingly, users under that manager's supervision can only submit access requests for applications that their manager is entitled to. This creates a streamlined, policy-driven workflow where a user's requests are automatically filtered to match their manager's permissions.

This enhancement significantly improves security by preventing unauthorized or out-of-policy application assignments. It reinforces the principle of least privilege and ensures that all access delegation is conducted within a controlled and logical framework.

#### 4. User Settings Permissions

* **User Lock & Unlock:** Allows the manager to lock or unlock user accounts.
* **User Delete:** Permits the manager to delete user accounts.
* **Reset Password:** Enables the manager to reset user passwords.

#### 5. RBAC Permissions

* **Assign RBAC Role:** Allows the manager to assign RBAC roles.
* **Unassign RBAC Role:** Permits the manager to unassign RBAC roles.

#### 6. Secret Question Permissions

* **Secret Question:** Grants access to view secret questions of team members.

#### 7. Additional MFA Permissions

* **Remove MFA For User:** Permits the manager to remove MFA for team members.

#### 8. User Status Permissions

* **Active User Status:** Sets a user's status to active.
* **Inactive User Status:** Sets a user's status to inactive.

#### 9. Risks and Violations Permissions

* **Risks and Violations:** Allows the manager to view risks and violations associated with team members.

### Configuration Steps

To configure Teams Config, follow these simple steps:

1. Navigate to Products -> Lifecycle Management -> Teams Config.

<figure><img src="../.gitbook/assets/image (463).png" alt=""><figcaption></figcaption></figure>

The administrator has a wide range of options, varying from basic user creation to assigning applications and managing roles, all within a structured framework.

A more elaborate list of options includes:

* Archived User
* Suspend User View
  * Suspend User Resume
  * Suspend User Delete
* Users
  * Create User
  * Update User&#x20;
  * User Info
  * User Application View
    * Assign Application
      * Manager Application
  * Assign Role
  * Unassign Application
  * Unassign Role
  * Menu Action
* User Groups View
  * Assign Group
  * Unassign Group
* User Settings
  * User Lock & Unlock
  * User Delete
  * Reset Password
  * RBAC
    * Assign RBAC Role
    * Unassign RBAC Role
* Secret Question
* Additional MFA
  * Remove MFA For User
* Active User Status
* Inactive User Status
* Risks and Violations
* Activity

An administrator can choose to Add a new Teams config or update an existing one. A newly added configuration can be both deleted and/or deactivated.

Add a new Teams config. Click on the +Add Teams Config button and a page as below will be shown:

**Name:** A name for the configuration

**Description:** A detailed description for the configurations

**Status:** Set to active for enabling the configuration

**Team:** A Set of permissions (as explained above) that the administrator can select from to provide different levels of access to the manager

**Conditions:** A Set of conditions (like _Country_, _Department_, _Designation_, _Login Pattern,_ and _UserType_) that the manager needs to satisfy for the permissions  to be provided to the manager

Additionally, the administrator can also set defined rules to apply the permissions for the same.

<figure><img src="../.gitbook/assets/image7 (4).png" alt=""><figcaption></figcaption></figure>

Cymmetri offers advanced settings for user creation and updates, providing administrators with fine-grained control over the onboarding process.

**Create User Advanced Settings**

This feature allows for extensive customization of the user registration process, which can be enabled or disabled via a simple toggle. The key configuration options include:

<figure><img src="../.gitbook/assets/unknown (59).png" alt=""><figcaption></figcaption></figure>

Activation Method: The administrator can choose how a new user receives their initial credentials:

1. Generate Activation Link: An activation link is sent to the user's email.

<figure><img src="../.gitbook/assets/unknown (60).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/unknown (61).png" alt=""><figcaption></figcaption></figure>

2. Generate Password: A system-generated password is created and provided to the user.

<figure><img src="../.gitbook/assets/unknown (62).png" alt=""><figcaption></figcaption></figure>

User Threshold: This setting defines the maximum number of new users that can be registered in a single batch.

<figure><img src="../.gitbook/assets/unknown (64).png" alt=""><figcaption></figcaption></figure>

Pre-Registration Hook: A script that executes before user registration is completed. This is useful for tasks such as data validation, modifying user attributes, or enforcing custom business rules.

<figure><img src="../.gitbook/assets/unknown (65).png" alt=""><figcaption></figcaption></figure>

Post-Registration Hook: A script that runs after user registration is successfully completed. This can trigger follow-up actions like sending a welcome email, logging details, or syncing with other systems.

<figure><img src="../.gitbook/assets/unknown (66).png" alt=""><figcaption></figcaption></figure>

User Registration Fields: Administrators can define and map the fields captured during the registration process.

<figure><img src="../.gitbook/assets/unknown (70).png" alt=""><figcaption></figcaption></figure>

This is managed through a table with the following columns:

* Field Label: The display name on the registration form.
* Field Name: The internal key for the field.
* Cymmetri Field: The Cymmetri user attribute it maps to.
* Required: Marks the field as mandatory.
* Regex: Allows for validation of input using regular expressions.
* Actions: Options to edit or delete the field.

<figure><img src="../.gitbook/assets/unknown (71).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/unknown (72).png" alt=""><figcaption></figcaption></figure>

Click on OK: It will display the message file updated successfully.

<figure><img src="../.gitbook/assets/unknown (78).png" alt=""><figcaption></figcaption></figure>

Click on OK: It will display the message Registration field saved successfully.

<figure><img src="../.gitbook/assets/unknown (74).png" alt=""><figcaption></figcaption></figure>

Click on Save: It will display the message Teams config updated successfully.

<figure><img src="../.gitbook/assets/unknown (79).png" alt=""><figcaption></figcaption></figure>

Navigate to My workspace and select a team.

<figure><img src="../.gitbook/assets/unknown (82).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/unknown (81).png" alt=""><figcaption></figcaption></figure>

Update the desired fields.

Click Save. A confirmation message, such as "teams config updated successfully," will be displayed.

<figure><img src="../.gitbook/assets/unknown (83).png" alt=""><figcaption></figcaption></figure>

#### Update User Advanced Settings

Similar to the creation settings, this feature gives administrators control over what happens when a user's information is updated. It includes Pre-Update Hooks and Post-Update Hooks to validate or transform data and trigger actions after a successful update. It also allows for the configuration of updatable user fields, including requirements and validation rules.

image

User Registration Configuration (Enabled/Disabled)

* Toggle to enable or disable self-service user registration.

<figure><img src="../.gitbook/assets/unknown (44).png" alt=""><figcaption></figcaption></figure>

Pre-Registration Hook

* A script section that runs before the registration process is completed.
* A script section that runs after the registration process is done.
* Useful for triggering actions like sending a welcome mail, logging details, or syncing with external systems.

&#x20;Post-Registration Hook

<figure><img src="../.gitbook/assets/unknown (45).png" alt=""><figcaption></figcaption></figure>

* Can be used to validate input, modify user data, or enforce custom business rules.

A table where you define which attributes (fields) are captured during user registration.

<figure><img src="../.gitbook/assets/unknown (47).png" alt=""><figcaption></figcaption></figure>

* Click on Add Registration Field

User Registration Fields

<figure><img src="../.gitbook/assets/unknown (46).png" alt=""><figcaption></figcaption></figure>

Columns explained:

* Field Label → Display name on registration form (e.g., First Name).
* Field Name → Internal field key (e.g., firstname, login).
* Cymmetri Field → Maps to Cymmetri’s user attribute.
* Required → Marks the field as mandatory.
* Regex → Allows input validation (e.g., only digits for mobile).
* Actions → Edit or delete the field.

<figure><img src="../.gitbook/assets/unknown (48).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/unknown (49).png" alt=""><figcaption></figcaption></figure>

Click on OK: It will display the message file updated successfully.

<figure><img src="../.gitbook/assets/unknown (50).png" alt=""><figcaption></figcaption></figure>

Click on OK: It will display the message Registration field saved successfully.

<figure><img src="../.gitbook/assets/unknown (51).png" alt=""><figcaption></figcaption></figure>

Click on Save: It will display the message Teams config updated successfully.

<figure><img src="../.gitbook/assets/unknown (52).png" alt=""><figcaption></figcaption></figure>

Go to My workspace: Select the team and try to update the user through the team.

<figure><img src="../.gitbook/assets/unknown (53).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/unknown (54).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/unknown (55).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/unknown (56).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/unknown (57).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/unknown (58).png" alt=""><figcaption></figcaption></figure>

### Default Configuration

There is a **Default Teams Config** that applies to all reporting managers. Any permission enabled here is universally applicable. It cannot be deleted but can be deactivated.

<figure><img src="../.gitbook/assets/image (467).png" alt=""><figcaption></figcaption></figure>

Customization based on specific conditions for a particular set of managers is not possible in this default configuration.&#x20;

<figure><img src="../.gitbook/assets/image (468).png" alt=""><figcaption></figcaption></figure>
