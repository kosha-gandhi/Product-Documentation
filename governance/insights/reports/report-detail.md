# Report Detail

### USER REPORTS

#### 1. Cymmetri Users Report

**Description:**\
Comprehensive master list of all users registered in Cymmetri across domains, employment types, and statuses.

**Explanation (Use Case):**\
HR or IT Admin needs a consolidated list of all active, inactive and deleted identities to reconcile with HRMS.\
Example: During quarterly audit, compliance team exports all active users to compare against payroll records.

**Filters Include:**

* Status (ACTIVE|INACTIVE|DELETE)
* User Type (Employee|Contractor|Vendor|Consultant|...)
* Designation
* Department
* Creation Date Range
* And many other fields on which the records can be filtered

Filters help narrow down the population for audit or operational purposes.

#### 2. Domain Admin Access Report

**Description:**\
Lists users who have administrative privileges at the domain level (domain administrators).

**Explanation (Use Case):**\
Security team reviews privileged users to ensure least-privilege compliance.\
Example: Quarterly privileged access audit to validate domain admins.

**Filters Include:**

* Domain Name
* Role Type
* Status (ACTIVE|INACTIVE|DELETE)
* User Type (Employee|Contractor|Vendor|Consultant|...)
* Designation
* Department
* Assignment Date Range
* And many other fields on which the records can be filtered

Helps isolate specific domain admin users during compliance review.

#### 3. Recent Hires Report

**Description:**\
Displays users who have been recently onboarded in Cymmetri having their account start date in the last 30 days.

**Explanation (Use Case):**\
HR validates whether all new joiners received system access.\
Example: HR runs weekly report to confirm provisioning SLA adherence.

**Filters Include:**

* Date of Joining
* Department
* Manager
* Employment Type
* And many other fields on which the records can be filtered

Useful to monitor onboarding effectiveness.

#### 4. Sunset User Report

**Description:**\
Users nearing contract end date or account expiration having their end date in the next 30 days.

**Explanation (Use Case):**\
IT proactively deactivates contractor accounts before expiration.\
Example: Avoid security risk from forgotten contractor accounts.

**Filters Include:**

* Contract End Date
* Employment Type
* Status
* Department

Helps identify users whose access should be reviewed soon.

#### 5. Terminated Users Report

**Description:**\
List of users who are either in suspended or archived state in Cymmetri

**Explanation (Use Case):**\
Ensures access revocation post-termination.\
Example: Audit confirms terminated employee accounts are disabled within SLA.

**Filters Include:**

* Termination Date
* Domain
* Application Assignment Status

Ensures no residual access remains.

#### 6. Users Without Reporting Managers

**Description:**\
Identifies users not mapped to a reporting manager.

**Explanation (Use Case):**\
Important for access review workflows where manager approval is mandatory.\
Example: Access request stuck because no reporting manager assigned.

**Filters Include:**

* Department
* Employment Type
* Domain

Helps correct organizational hierarchy gaps.

#### 7. Cymmetri Usage Report

**Description:**\
Displays a consolidated list of users who have been involved in any activity within Cymmetri—either as recipients of actions (such as email notifications or application assignments) or as actors who performed actions within the system.

**Explanation (Use Case):**\
The CISO reviews user activity and engagement across the platform to assess overall adoption and operational usage.

Example: Track the percentage of users who have performed actions in Cymmetri (e.g., SSO login, access requests, approvals) versus users with no recorded activity.

**Filters Include:**

* Date Range
* Domain
* User Type

Provides insight into engagement trends.

#### 8. User Login Report

**Description:**\
Tracks user login activity including login status count (SUCCESS, FAILED, TOTAL).

**Explanation (Use Case):**\
The Security team monitors login behavior to detect anomalies, potential brute-force attempts, or compromised accounts.\
Example: Identify users with repeated failed login attempts within a specific time window and trigger investigation or account lock policies.

Filters Include:

* Date Range
* Login Status (Success/Failure)
* MFA Used
* Domain

Useful for security investigations.

### APPLICATION REPORTS

#### 9. Application Access

**Description:**\
Shows which users has accessed to a particular application and the time it was accessed.

**Explanation (Use Case):**\
App owner validates access list before audit.\
Example: Finance application owner reviews all the users who have accessed an particular finance app in the last month.

Filters Include:

* Application Name
* Status
* User Type
* Department
* Designation

#### 10. Application Assignment Report

**Description:**\
Details user-to-application assignments including role mapping, the assignment status and user status.

**Explanation (Use Case):**\
Governance team verifies provisioning and deprovisioning process execution.\
Example: Check if a user has received CRM App successfully.

**Filters Include:**

* Application Name
* Application Status
* User Type
* User Status

#### 11. Provisioning Report

**Description:**\
Tracks provisioning and de-provisioning activities.

**Explanation (Use Case):**\
Operations team monitors provisioning success/failure.\
Example: Identify failed SAP account creation attempts.

**Filters Include:**

* Application
* Status (Success/Failed)
* Date Range
* Provisioning Type

#### 12. Unused Roles Report

**Description:**\
Roles assigned but not actively used.

**Explanation (Use Case):**\
Remove redundant or dormant access.\
Example: Users assigned ERP role but never logged in.

**Filters Include:**

* Application
* Role
* Last Used Date
* Department

#### 13. Application Usage Report

**Description:**\
Shows frequency of application access.

**Explanation (Use Case):**\
License optimization.\
Example: Reduce SaaS licenses for inactive users.

**Filters Include:**

* Application
* Date Range
* Department
* Usage Count Threshold

#### 14. MFA Usage Report

**Description:**\
Tracks MFA adoption and method usage.

**Explanation (Use Case):**\
Security team ensures compliance with MFA policy.\
Example: Identify users not enrolled in MFA.

**Filters Include:**

* MFA Type (OTP, Push, FIDO)
* Date Range
* Domain
* User Status

#### 15. Most Active Users Report

**Description:**\
Users with highest login/application activity.

**Explanation (Use Case):**\
Detect unusual activity or identify power users.\
Example: Monitor privileged users with high system access.

**Filters Include:**

* Date Range
* Application
* Department

### ADMINISTRATOR REPORTS

#### 16. Cymmetri Administrators

**Description:**\
List of platform administrators and their assigned roles.

**Explanation (Use Case):**\
Periodic privileged access review.

**Filters Include:**

* Role
* Domain
* Status

#### 17. Cymmetri Audit Report

**Description:**\
Detailed log of events/actions performed within Cymmetri (config changes, approvals, provisioning actions, etc.).

**Explanation (Use Case):**\
Used during regulatory audit to trace “who did what and when.”\
Example: Audit confirms who modified an SoD policy.

**Filters Include:**

* Event Type
* Date Range
* Admin/User
* Module (IGA, SSO, PAM)

### CONTRACT & EMPLOYEE REPORTS

#### 18. Contractors with Upcoming Contract End Date

**Description:**\
Lists contractors nearing contract expiry.

**Use Case:**\
Prevent orphan accounts.

**Filters:**

* End Date Range
* Department
* Manager

#### 19. Employees with Upcoming Contract End Date

**Description:**\
Employees nearing employment contract completion.

**Use Case:**\
Initiate access review before contract renewal decision.

**Filters:**

* Date Range
* Department

#### 20. Terminated Contractors Report

**Description:**\
Tracks terminated contractor accounts.

**Use Case:**\
Verify de-provisioning.

**Filters:**

* Termination Date
* Application Access Status

#### 21. Terminated Employees Report

**Description:**\
Tracks terminated employees and access removal.

**Use Case:**\
Compliance audit validation.

**Filters:**

* Date Range
* Domain
* Access Status

### RISK-BASED REPORTS

#### 22. Aggregate Risk Report

**Description:**\
Displays overall risk score across users and applications.

**Explanation (Use Case):**\
CISO views risk posture of entire organization.\
Example: Identify departments with high risk exposure.

**Filters Include:**

* Risk Score Range
* Department
* Application
* Role

#### 23. Application Risk Report

**Description:**\
Risk score at application level.

**Explanation (Use Case):**\
Prioritize access review for high-risk applications like core banking.

**Filters Include:**

* Application
* Risk Level
* Domain

### USER ACCESS REVIEW REPORTS

#### 24. Access Review/Certification Report – New

Description:\
Details ongoing and completed certification campaigns.

Use Case:\
Audit-ready evidence of access governance.

Filters:

* Campaign Name
* Status
* Reviewer
* Date Range

#### 25. Application Access (Review Context)

**Description:**\
Access details of users under certification.

**Use Case:**\
Manager validates access during review.

**Filters:**

* Application
* Campaign
* Reviewer

#### 26. Completed Access Review

**Description:**\
Records finalized certification campaigns.

**Use Case:**\
Provide evidence to regulators.

**Filters:**

* Completion Date
* Campaign
* Application

#### 27. Domain Admin Access Report (Review Context)

**Description:**\
Privileged domain admins under certification scope.

**Use Case:**\
Special focus review for high-risk roles.

**Filters:**

* Domain
* Campaign
* Risk Score

#### 28. Running Access Review

**Description:**\
Displays in-progress certification campaigns.

**Use Case:**\
Track completion percentage and pending approvals.

**Filters:**

* Campaign Status
* Reviewer
* Application
