# Compliance Management

### Certification and Attestation

Cymmetri Identity Governance provides for managing user certification through its [**Campaign Management**](../access-certification/) feature. As part of user access review, a campaign can be set up to automatically process the user entitlements and send the review request to the appropriate approvers in the system.

&#x20;The campaign allows review of

●       All users

●       Groups of users

●       Type of users (employees, vendors)

●       Application wise users

The system allows the review to occur in stage-wise approval allowing up to 3 levels of certification.

The campaign can be setup to occur periodically using Cymmetri’s scheduler.

&#x20;At the review side, the mapped approver user can view and approve the certification in **Self service** console of Cymmetri. The approver can certify in bulk by either approving or revoking the access of the required users. The revocation of access is in real-time. To read more and configure refer [this](../access-certification/).

### Unstructured Data Attestation

As an add on component, Cymmetri allows request provisioning for Windows File System share folders utilizing PowerShell connector. Cymmetri can also perform periodic reviews of the resources and permissions available with users.

### Segregation Of Duties

As a part of strong governance controls, Cymmetri provides configuration for [**Segregation Of Duties**](../segregation-of-duties-sod.md) or **SoD** through the Admin console. Every large organization faces the complexity of providing adequate access to its users to allow business as usual practices. However, over time, as more applications and their entitlements come into play, the ability to restrict the access controls involves greater risk.

Cymmetri’s SoD attempts to mitigate the access gaps and more then required access to users by defining appropriate business roles and responsibilities and managing them over a long period of time. Cymmetri breaks the configuration down to two main aspects:

1. Defining the business functions through
   1. Process
   2. Tasks
   3. Business Roles
2. Defining the access policy
   1. Business Policy
   2. Rules

Once the above definitions are understood and configured manually or through bulk-upload, the system can begin processing risk scores and access violations for individual users based on their existing entitlements.

The violations allow the business line managers and risk management to understand the access rights in violation. The violations are based on the business policy and rules which are in violation of the tasks that might be in conflict for business roles.

Apart from the violations, the system calculates and assigns a risk score to every user and their application entitlements. Based on the application roles in the target system, Cymmetri generates a qualitative risk score combining all the applications and entitlements.

A qualitative risk score will be assigned based on the application risk factor and overall risk across all applications associated with the user. To read more and configure refer [this](../segregation-of-duties-sod.md).

### IAM Reporting

Cymmetri allows monitoring of key IAM metrics as per the [Cymmetri reports](../insights/reports.md) under Insight menu. To read more and configure refer [this](../insights/reports.md).

Apart from the out of box reports, Cymmetri provides custom reporting and dashboards which provide the ability to view the Cymmetri data as per specific needs. This is possible through Cymmetri's [Analytics](../../analytics/cymmetri-analytics.md) module.

### Overview of the policies that can be enforced from Cymmetri

* [Authentication Policy](../../identity-hub/authentication/) & [Rules](../../identity-hub/authentication/authentication-rules.md)
* [Password Policy](../../identity-hub/authentication/password-policy.md)
* [Provisioning Policy](../../lifecycle-management/application-management/provisioning-how-to/) & [Rules](../../lifecycle-management/application-management/provisioning-how-to/)
* [De-provisioning Policy](../../lifecycle-management/application-management/rules/deprovisioning.md)
* [Segregation Of Duties & Violation Policies](../segregation-of-duties-sod.md)
* [Multi-Factor based Authentication](../../single-sign-on/multifactor-authentication-mfa/)&#x20;
* [Passwordless Authentication](../../single-sign-on/passwordless/)
* [Privileged Access Policy](broken-reference)
* [IGA Policy Management](iga-policy-violations.md)
