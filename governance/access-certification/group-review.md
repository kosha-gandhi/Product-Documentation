# Group Review

Cymmetri's Group Access Review functionality has been enhanced to provide administrators with more granular control over the scope and execution of access review campaigns. This feature streamlines the process of auditing group memberships and user entitlements, ensuring greater security and compliance.

Administrators can now initiate access reviews based on the following flexible criteria:

* **All Groups**: This option enables a comprehensive, organization-wide review of all group memberships. This is particularly useful for broad security audits, annual compliance checks, and ensuring a clean slate of group entitlements.
* **Specific Multiple Groups**: This allows for a targeted review of several pre-selected groups simultaneously. This is ideal for focused security assessments, such as reviewing all groups associated with a high-risk project or auditing groups that contain external collaborators.
* **Specific Multiple Applications**: This feature allows administrators to conduct a single review covering multiple applications at once. This ensures that access policies are consistently enforced across a suite of critical or high-risk applications.

**Step 1**: The initial setup for these campaigns follows the same established procedure as other Cymmetri [Campaigns](setting-up-and-managing-access-reviews.md).

<figure><img src="../../.gitbook/assets/image (60).png" alt=""><figcaption></figcaption></figure>

**Step 2**: Selection and Exclusion: Administrators have the flexibility to select specific groups for inclusion in the review and can also exclude groups that are not relevant to the current audit. This precision ensures that the review is focused and efficient.

<figure><img src="../../.gitbook/assets/image6 (6).png" alt=""><figcaption></figcaption></figure>

**Step 3**: Approver Designation: The administrator can designate an approver from a range of options, including:

* **A specific user**: This is the most straightforward method. An administrator can manually select a specific user to act as the approver for the entire campaign.
* T**he reporting manager of the user**: This option automates the approval workflow based on the organizational hierarchy. The system automatically routes the access review request to the reporting manager of the user whose access is being reviewed.

Annotations: This provides a highly advanced and dynamic method for approver designation. Instead of manually selecting an individual, administrators can use annotations to create rule-based approval workflows, allowing for complex and context-aware approver assignments.

<figure><img src="../../.gitbook/assets/image (61).png" alt=""><figcaption></figcaption></figure>

**Step 4**: Notification Settings: The administrator can configure customized notification settings to alert approvers and users about the campaign's status and required actions.

<figure><img src="../../.gitbook/assets/image (56).png" alt=""><figcaption></figcaption></figure>

All past and present group reviews are logged under Group Access Review → Campaign History. The campaign logs the following data points:

Campaign Overview:

* Campaign Name: The name of the campaign.
* Iteration: The number of times the users' access has been reviewed.
* Total Assignments: The total count of user assignments, including roles and applications.
* Start Date: The date the campaign was initiated.
* Planned End Date: The administrator-defined end date.
* Start Mode: The initiation mode of the campaign (MANUAL or AUTO).
* End Mode: The termination mode of the campaign (MANUAL or AUTO).

Detailed Assignment Information:

* Group Name: The name of the group a user belongs to.
* Member User: The name of the user in the corresponding group.
* Member Login: The login ID of the user.
* Group Type: The type of group (e.g., Local or Remote Group).
* Application Count: The number of applications associated with the user.
* Assignee: The user designated to approve or reject the access.
* Reviewed At: The timestamp when the approver completed the review.
* Stage: The specific stage at which the approver acted.
* Status: The final status of the approval (Approved or Rejected).
* Recommended History: Suggestions for risk mitigation actions for high-risk users, such as monitoring user activity or reviewing certifications.

<figure><img src="../../.gitbook/assets/image7 (2).png" alt=""><figcaption></figcaption></figure>

End-users and designated approvers can view active campaigns requiring their attention by navigating to Access Review → Identity Governance → Active → Group.

<figure><img src="../../.gitbook/assets/image5 (4).png" alt=""><figcaption></figcaption></figure>

From this interface, users can perform necessary actions to approve or reject requests. The available information includes:

* Campaign Overview (as detailed in the Campaign History section).
* Detailed Assignment Information (as detailed in the Campaign History section), with an additional column for actions.
  * Actions: The option to approve or reject the assignment.

<figure><img src="../../.gitbook/assets/image (57).png" alt=""><figcaption></figcaption></figure>

The user can also apply filters based on the actions that need to be taken.

<figure><img src="../../.gitbook/assets/image2 (7).png" alt=""><figcaption></figcaption></figure>

Users can also apply filters to streamline their view based on specific criteria:

* Status: Filters assignments by their state (Pending Approval, Approved, or Rejected).
* Stage: Allows users to filter by a specific review stage.
* Filter: Distinguishes between user- and group-based assignments.
* Users: Allows the approver to filter for a specific user within the campaign.

<figure><img src="../../.gitbook/assets/image3 (6).png" alt=""><figcaption></figcaption></figure>
