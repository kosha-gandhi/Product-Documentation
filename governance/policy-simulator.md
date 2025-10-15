# Policy Simulator

The Policy Simulator is a feature that enables administrators to define, test, and enforce security policies proactively. This mechanism enables the validation of existing system and application configurations against predefined policies, ensuring continuous compliance and security.

Administrators can use the Policy Simulator to create detailed policies based on various attributes of users, applications, and their entitlements. The feature supports the creation of highly customized rules using direct queries in databases like MongoDB and ClickHouse. The simulation process involves two primary components:

* Left-Hand Side (LHS): A defined set of entitlements, which can include users, applications, roles, or groups. This represents the scope of the policy you are testing.
* Right-Hand Side (RHS): A separate set of entitlements that the LHS is compared against. This establishes the condition or state that is being validated.

The system then evaluates these two sets of entitlements to identify any scenarios where users or their access rights violate the defined policies. This granular comparison provides precise insights into where an organization's security posture may be weak.

This feature provides a robust and proactive approach to IAM governance, enabling organizations to move beyond reactive security measures and maintain a consistently secure and compliant environment.

The Policy Simulator can be accessed by navigating to Identity Governance → Policy → Simulator.

<figure><img src="../.gitbook/assets/image (58).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image6 (4).png" alt=""><figcaption></figcaption></figure>

Configuration Steps

1. Define Policy Attributes: Begin by providing core details for the new policy:

* Policy Name: A clear, descriptive name for the policy.
* Policy Description: A brief explanation of the policy's purpose and scope.
* Policy Violation Risk: Assign a risk level (High, Medium, or Low) to indicate the severity of a policy violation.

2. Establish Policy Rules (LHS-RHS): The Policy Simulator operates on an if-then or Left-Hand Side (LHS) - Right-Hand Side (RHS) rule-based logic. The administrator must define both conditions to create a complete policy:

* LHS: This defines the "if" condition, representing a set of entitlements (users, applications, roles, or groups) that you want to evaluate.
* RHS: This defines the "then" condition, representing the set of entitlements you are comparing against. The simulator identifies any instances where the LHS entitlements do not align with the RHS conditions, indicating a policy violation.

<figure><img src="../.gitbook/assets/image9 (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image14 (1).png" alt=""><figcaption></figcaption></figure>

The administrators can schedule policy execution and automate report delivery, ensuring continuous monitoring and compliance. This feature streamlines the process of auditing user entitlements against predefined security policies.

<figure><img src="../.gitbook/assets/image3 (7).png" alt=""><figcaption></figcaption></figure>

#### Scheduling a Policy Run

To schedule a policy, the administrator must provide the following details:

* Schedule After: The specific date on which the administrator wants the policy simulation to begin.
* Cron Expression: A time-based expression that defines the exact execution time. Administrators can configure the policy to run on an hourly, daily, weekly, monthly, or even yearly basis. This allows for a high degree of flexibility in aligning policy checks with organizational security cadences.

By automating these runs, administrators can transition from reactive to proactive security management, ensuring that policy violations are consistently detected and reported.

<figure><img src="../.gitbook/assets/image4 (6).png" alt=""><figcaption></figcaption></figure>

Upon execution, the system can automatically generate a report of all identified policy violations. This report is delivered to specified recipients in a CSV file format, which is ideal for data analysis and integration with other systems.

* Recipient Notification: The administrator can enable a notification and provide the email addresses of the desired recipients. This ensures that relevant stakeholders, such as security analysts, compliance officers, or managers, are immediately informed of any new policy violations.

<figure><img src="../.gitbook/assets/image (59).png" alt=""><figcaption></figcaption></figure>

All scheduled policies are listed under the Policy Scheduler section of the Cymmetri interface. This provides administrators with a centralized view of all active scheduled jobs, allowing for easy management and modification.&#x20;

<figure><img src="../.gitbook/assets/image8 (1).png" alt=""><figcaption></figcaption></figure>

#### Reviewing and Managing Policy Reports

After a policy has been configured and published, the generated data is made available to the administrator in the Library section of the Identity Governance module.

<figure><img src="../.gitbook/assets/image2 (8).png" alt=""><figcaption></figcaption></figure>

Within the specific policy's entry, you can view the detailed results, which include:

* Run Mechanism: The mode of policy execution (e.g., manual, scheduled).
* User Details:
* User Display Name, User Login, Department, Designation: Standard user information.
* Status: Whether the user is active or inactive.
* Country and Manager ID: Geographical and hierarchical user details.
* User Type: The user's category, such as Consultant, Vendor, or Employee.
* User Risk: An assessed risk level associated with the user's entitlements.
* Application Name, Group Name, Role Name: The specific entitlements that violate the defined policy.

<figure><img src="../.gitbook/assets/image7 (3).png" alt=""><figcaption></figcaption></figure>

#### Report Management and History

The administrator can share the generated reports with relevant stakeholders. These reports are provided in a CSV format for easy data analysis.

<figure><img src="../.gitbook/assets/image11 (1).png" alt=""><figcaption></figcaption></figure>

All previously created and run policies are accessible for review and historical analysis under the History tab, providing a complete audit trail of policy enforcement activities.\


<figure><img src="../.gitbook/assets/image1 (12).png" alt=""><figcaption></figcaption></figure>

After an administrator has created and run a policy in the Policy Simulator, the system generates a detailed report of all identified violations. To initiate a remediation campaign based on these violations, the administrator can select the "Start Campaign for Policy" option. This feature automates the creation of a new access review campaign, pre-populating it with the specific users and entitlements that were flagged in the policy report. This streamlines the process, eliminating the need for manual data transfer and ensuring a direct and efficient path to remediation.

<figure><img src="../.gitbook/assets/image10 (3).png" alt=""><figcaption></figcaption></figure>

To simplify the review process and focus on relevant data, the administrator has the ability to apply filters. These filters allow for a more granular view of the data by isolating specific attributes. This is especially useful for large reports, as it helps in prioritizing critical violations.

<figure><img src="../.gitbook/assets/image15 (3).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image5 (7).png" alt=""><figcaption></figcaption></figure>

After applying the desired filters and selecting the columns to display, the administrator can view a clean, organized dataset. This provides all the necessary information to make informed decisions and take the appropriate action on the policy violations.

<figure><img src="../.gitbook/assets/image12 (4).png" alt=""><figcaption></figcaption></figure>

Refer for creating [Campaigns](access-certification/).\
\
