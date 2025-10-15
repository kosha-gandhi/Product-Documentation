# Delete Users

In user lifecycle management, the transition of a user's status from Suspended to Archived initiates a critical de-provisioning sequence. This process is designed to ensure that all user entitlements are permanently revoked from target applications, a final action controlled by a configurable flag.

**User Creation and Initial Status**: The process begins with a user being created in the system, with their initial status set to Active.

<figure><img src="../../.gitbook/assets/image2 (12).png" alt=""><figcaption></figcaption></figure>

**Suspension Initiation**: An administrator initiates the suspension of a user by selecting the "Delete User" option. This action changes the user's status to Suspended, thereby revoking their login privileges while retaining their account information.

<figure><img src="../../.gitbook/assets/image5 (9).png" alt=""><figcaption></figcaption></figure>

**Movement to Suspended List**: The user's profile is then moved to the Suspended Users list, allowing administrators to differentiate between active and temporarily disabled accounts.

<figure><img src="../../.gitbook/assets/image4 (8).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image7 (6).png" alt=""><figcaption></figcaption></figure>

**Log Verification**: The administrator can verify this status change by reviewing the system logs. The logs will record the status transition from "ACTIVE" to "DELETE." This log entry also provides a clear record of the user's application status, indicating if any associated applications were also de-provisioned at this stage.

<figure><img src="../../.gitbook/assets/image1 (14).png" alt=""><figcaption></figcaption></figure>

**Forced Deletion**: Should the administrator require immediate, permanent de-provisioning, the "FORCE DELETE" option can be used. This action bypasses the standard suspended state and triggers the final de-provisioning call immediately, ensuring that all entitlements are permanently removed.

<figure><img src="../../.gitbook/assets/image6 (8).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image3 (9).png" alt=""><figcaption></figcaption></figure>

**Final Validation**: To confirm the user's complete de-provisioning, the administrator can once again validate the status in the system logs. The logs will confirm the final deletion and provide a complete audit trail of the user's lifecycle, from creation to final de-provisioning.
