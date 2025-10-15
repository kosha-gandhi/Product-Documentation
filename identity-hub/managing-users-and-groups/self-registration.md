# Self Registration

Self-registration empowers users with greater control over their accounts, reducing the administrative burden on IT and security teams. These enhancements focus on a secure and streamlined self-registration process and improved password management.

#### New Features:

* Configurable Self-Registration: Cymmetri now supports self-registration, allowing new users to create their accounts securely. This process is governed by pre-defined parameters and policies, ensuring that all new accounts meet your organization's security and compliance standards from the outset.
* Activation and Password Management:
* Activation Link: Once a new user self-registers, the system automatically sends them an activation link. This link allows them to set their own secure password, finalizing their account setup.
* Password Reset Link: For existing users, administrators, or managers can now easily send a password reset link. This empowers users to securely reset their login credentials independently, eliminating the need for manual password changes by support staff.

These updates automate key user management tasks, providing a more efficient and secure experience for both users and administrators.

<figure><img src="../../.gitbook/assets/image3 (8).png" alt=""><figcaption></figcaption></figure>

To enable and manage these features, administrators must perform the following configuration steps:

1. Access Configuration Settings: Navigate to Configuration → Self Registration Config within the Cymmetri interface.
2. Choose Password Generation Method: The administrator has two primary options for password management:
3. Generate Activation Link: This option, as described above, sends a link to the user, allowing them to create their own password.
4. Generate Password: This alternative automatically generates a temporary password that the user must use to log in for the first time before being prompted to change it.
5. Configure Hooks and Registration Fields:
6. Pre-Hook and Post-Hook: The administrator must set up both pre-hook and post-hook configurations. These are custom scripts or actions that can be run before or after a new user account is created, allowing for custom validation or integration with other systems.
7. User Registration Fields: The administrator must define the fields that will be displayed to users during the self-registration process (e.g., First Name, Last Name, Email, Department).

Add Custom Fields: For increased flexibility, the administrator can add new User Registration Fields by clicking + Add Registration Field, allowing for the collection of additional information relevant to the organization.

<figure><img src="../../.gitbook/assets/image1 (10).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image2 (10).png" alt=""><figcaption></figcaption></figure>
