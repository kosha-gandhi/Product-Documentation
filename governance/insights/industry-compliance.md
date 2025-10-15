# Industry Compliance

Cymmetri is built in accordance to industry regulations and guidelines.&#x20;

## Insurance Regulatory and Development Authority of India(IRDAI)

Below are the IRDAI relevant control objectives.&#x20;

### Data Classification

| Key Points                                                                                                                                                                                                                                                                                          | Cymmetri Coverage                                                                                                                                                                                                                            |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| The Information Owner shall only classify information assets within their purview using one of the following four classification levels: Public, Internal, Restricted, Confidential. Classification levels shall be defined based on the information asset’s relative risk, value, and sensitivity. | Cymmetri will allow the right user to access the right application with the right context based on the access policies defined in Cymmetri platform. Applications can internally manage the data classification for asset's risk management. |
| All Information assets should have a designated owner, Owner may delegate ownership to others, but will be accountable for the same                                                                                                                                                                 | Cymmetri will protect access to application resources by allowing the appropriate user to the required resources. The information owner may allow delegation if allowed through Cymmetri access policies.                                    |

### Access Control

| Key Points                                                                                                                                                                                                      | Cymmetri Coverage                                                                                                                                    |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| A User-ID or account shall be assigned to each individual to authorize a defined level of access to information assets and shall be protected by authenticating the user to the User-ID upon requesting access. | Cymmetri IDAM allows creation and maintenance of clean user identities for purpose of authorization to resources and authentication to applications. |

### **Generic Ids**

| Key Points                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   | Cymmetri Coverage                                                                                                                                                                                                                                                                                                                                                                                                             |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| The use of generic and group User-IDs shall be avoided wherever possible. Wherever there is no alternative available / it is absolutely essential a group account shall be used; however, it shall follow the Exception grant and risk assessment methodology requiring the prior authorization of the appropriate authorities and clear accountability to one individual (Group ID owner) shall be established. The use of Group-ID shall be short term in nature having an expiration date | Cymmetri principally works with one-user-one-identity. However, for exception cases, Cymmetri allows mapping of generic-IDs to specific individual accounts and maintain the details of all access events using such generic accounts. Cymmetri platform grants access based on defined workflows for access to generic accounts along with periodic access reviews as well as defined end-of-access date for such scenarios. |
| An owner shall be identified for every generic User-ID created and the owner shall be held accountable for all actions associated with the generic User-ID. Where it is required for a generic User-ID to be shared between multiple individuals, alternative solutions for assigning and ascertaining accountability at all times shall be evaluated for feasibility and shall be implemented.                                                                                              | Cymmetri principally works with one-user-one-identity. However, for exception cases, Cymmetri allows mapping of generic-IDs to specific individual accounts and maintain the details of all access events using such generic accounts. Cymmetri platform grants access based on defined workflows for access to generic accounts along with periodic access reviews as well as defined end-of-access date for such scenarios. |

### Provisioning

<table data-full-width="false"><thead><tr><th width="377">Key Points</th><th width="584">Cymmetri Coverage </th></tr></thead><tbody><tr><td>Access to Organization’s environment such as the network shall be granted only upon intimation received from HR. All users shall be granted access to the information systems and services through a formal user registration process that shall include the approval of access rights from authorized personnel before granting access.</td><td><p>Cymmetri IDAM manages all users through</p><p>Identity Hub which maintains all organization </p><p>users including employees and third-party users. </p><p>Access grants to enterprise resources shall be </p><p>applied through Cymmetri Provisioning Rules </p><p>framework.</p></td></tr></tbody></table>

### Deprovisioning

| Key Points                                                                                                                                                                                                                                                                                                                                                                       | Cymmetri Coverage                                                                                                                                                  |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| All users shall follow a formal de-registration process for revocation of access to all information systems and services which shall include automated or timely intimation and revocation of access rights. Intimation for revocation of access rights shall come from HR. A confirmation of the access revocation shall be sent to HR as a part of the exit clearance process. | Cymmetri IDAM can automatically remove all access entitlements for a user based on source system of truth & internal access policies to ensure clean exit process. |

### SOD

| Key Points                                                                                                                                                                                                                                           | Cymmetri Coverage                                                                                                                                    |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| Levels of access granted to all Users shall enforce segregation of duties and adhere to the “need to know” principle. Where segregation of duties cannot be enforced by logical access controls, other non-IT-related controls shall be implemented. | Cymmetri IDAM allows configuration of an organizations business policies and tasks w.r.t. to access to application and their roles to establish SoD. |

### Password Policy

<table><thead><tr><th>Key Points</th><th>Cymmetri Coverage</th><th data-hidden></th></tr></thead><tbody><tr><td>An initial password shall be provided to the users securely during the user creation process and the system shall be configured to force the users to change the initial password immediately after the first logon.</td><td>Cymmetri enforces password policy on its users such as creating a new password after first logging into the system.</td><td></td></tr><tr><td>Appropriate procedures shall be put in place for storing and management of administrative passwords for critical information systems. All user passwords shall be encrypted while in transmission and storage.</td><td>Cymmetri securely manages all passwords by the use of strong cryptography controls. This ensures secure relay and storage of such information.</td><td></td></tr><tr><td>The password requirements for all user accounts shall follow the password standards as defined in the Password Standard. Any exceptions to the password standard shall follow the Exception grant and risk assessment methodology requiring the prior authorization of the appropriate authorities and counter measures shall be implemented to mitigate the resulting risk.</td><td>Cymmetri policy enforces password for all users. For varying use cases, Cymmetri can allow a differential password policy for certain users which can be enforced using appropriate controls in place such as approvals.</td><td></td></tr><tr><td>Users shall be required to change their passwords once in 45 days</td><td>Part of default Cymmetri password policy</td><td></td></tr><tr><td>A record of previously used passwords shall be maintained to prevent re-use. Further, password files shall be stored separately from application system data.</td><td>Part of default Cymmetri password policy. All passwords are stored separately and not part of user profile or application data.</td><td></td></tr></tbody></table>

### Recertification/Access Control

| Key Points                                                                                                                                                                                       | Cymmetri Coverage                                                                                                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| In case of transfer of an employee from one function to another, access rights of the user shall be revoked for previous functional role and access need to be provided for new functional role. | Cymmetri Provisioning Rules allow for setting up access grants based on role / attributes associated with user. On the event of a transfer, Cymmetri shall automatically remove access to previous entitlements and provision to new roles associated with the user. |

### User Authorization

| Key Points                                                                                                                                                                                                                                                       | Cymmetri Coverage                                                                                                                                  |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| User authorization mechanisms at each level shall be independent of authorization at a previous or subsequent level – for example, applications shall perform assessment of user authorization request independent of the operating system authorization process | All authorization events in Cymmetri are independent and not derived based on previous or next approver associations.                              |
| Users shall be authenticated and authorized by a domain policy server.                                                                                                                                                                                           | Cymmetri allows federated identity management principles, and thus, shall use an external identity provider for authentication such as AD or LDAP. |

### EndPoint Security

| Key Points                                                                                                                                                          | Cymmetri Coverage                                                                                                                                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Access to all endpoints and applications shall be permitted only after authorization of the user credentials by the host operating system or the application itself | Cymmetri allows for dual authentication strategy such as application access or during device authentication by user. The authentication policy can also force Multi-factor authentication to ensure strong authentication for all users. |

### Ruled Based Authentication

| Key Points                                                                                                                                                                                                                                                          | Cymmetri Coverage                                                                                                                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| If the authorization request comes from a Organization owned asset (device/network), single factor authentication will suffice. In case the authorization request comes from a non Organization asset (device/network) two-factor authentication will be mandatory. | Cymmetri IDAM has configurable MFA options and rules to invoke strong authentication principles.                                                                                                             |
| Applications hosted on the Cloud shall accept a user authorization record validated by a Organization-owned authorization service or require two factor authorization                                                                                               | Cymmetri enables organizations to specify the authentication source as part of the authentication policy. The policy will also invoke MFA based on rules defined or adaptive controls available in Cymmetri. |
| Users shall be required to re-authenticate themselves after a specific period of inactivity.                                                                                                                                                                        | Cymmetris' session management asks users to re-authenticate themselves after a given period of inactivity.                                                                                                   |
| Activity from all logons with Privileged User ID shall be securely logged.                                                                                                                                                                                          | All authentication requests are logged in Cymmetri platform.                                                                                                                                                 |

### Secure Logon

| Key Points                                                                                                                                                                                                                        | Cymmetri Coverage                                                                                                                            |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| Account lockout shall be enforced by the log-on process after the retry limit is reached                                                                                                                                          | Cymmetri authentication policy allows account lock and unlock thresholds to be defined.                                                      |
| Log of unsuccessful and successful attempts shall be maintained.                                                                                                                                                                  | In Cymmetri, all access logs are maintained for audit purpose with essential data points - who, when, what, and from where                   |
| The log-on process shall terminate inactive sessions after a defined period of inactivity, especially in high risk locations such as public or external areas outside the organization’s security management or on mobile devices | The session management principle enforces the timeout of the session from Cymmetri and compliant SSO applications integrated with Cymmetri.  |

### Recertification

| Key Points                                                                                                                                                       | Cymmetri Coverage                                                                                                                                                         |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Authorizations for privileged access rights shall be reviewed at more frequent intervals and changes to privileged accounts shall be logged for periodic review. | Cymmetri IDAM allows Access Governance through predefined campaigns which allow the approving authority to validate access rights of user, including privileged accounts. |

### Remote Access

| Key Points                                                                                                                                                                                                                                                                                                                                                                                                              | Cymmetri Coverage                                                                                                                                                                                                                                                                                                                                 |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Remote access request for third party vendor/consultant shall be raised by the Organization Employee responsible for the vendor /consultant engagement along with proper business justification. The request needs to be approved by sponsoring functional manager, Head – IT and Group CISO. If access is provided from non Organization endpoints an exception shall be taken in this regards Head-IT and Group CISO. | Cymmetri's configurable workflows allow organizations to setup user request and approvals process for granting of access to application resources on a time bound manner. This control ensures check of appropriateness of access requests as well as maintains an audit log of all such grants (or reject of grant) by the approving authorities |
| An expiration of not more than 15 days or lesser shall be placed on all third party user-IDs unless appropriate approval is given. Expiration of IDs will occur in the authenticating database. After the expiration, third parties who wish to continue working for Organization should obtain approval in order to regain the User-ID.                                                                                | The Time based access policy for granting access to users in Cymmetri controls access for any type of user. The user may be allowed to extend access based on appropriate approvals for such extension of access to specified applications.                                                                                                       |
| Remote access solutions must support strong, end-to-end encryption as mentioned in Organization’s policy for Cryptographic Controls.                                                                                                                                                                                                                                                                                    | Cymmetri employs strong cryptographic controls which are at par or exceed standard encryption methodologies.                                                                                                                                                                                                                                      |
| A remote log-on procedure shall be designed with consideration of encryption of information during its transmission. A secure network channel shall be established for remote access.                                                                                                                                                                                                                                   | All access to privileged resources are over secure channels with appropriate authentication principles ensuring secure transmission of data.                                                                                                                                                                                                      |
| Organization security solutions and controls shall not be disabled or circumvented.                                                                                                                                                                                                                                                                                                                                     | Cymmetri access controls do not allow circumvention. In case of emergencies, a break-glass type scenario allows emergency access to critical assets as a one-time event.                                                                                                                                                                          |

### Compliance and Audit&#x20;

| Key Points                                                                                                                                                                | Cymmetri Coverage                                                                                                                                                                                                                                              |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Remote Access System Owners shall maintain evidence of all requests for granting remote access                                                                            | In Cymmetri, all access logs are maintained for audit purpose with essential data points - who, when, what, from where                                                                                                                                         |
| All evidence for granting, revoking, or changing remote access privileges shall be maintained in a repository                                                             | With detailed audit and reporting capabilities, Cymmetri ensures access to privileged resources is logged for to ensure compliance                                                                                                                             |
| On a monthly basis, the system owner’s shall ensure that the accounts active within the Remote access solutions are accurate. All discrepancies shall be resolved quickly | Cymmetri IDAM allows Access Governance through predefined campaigns running at required intervals for regular users as well as privileged users to mapped approving authority, thus ensuring the active users continue to have appropriate access to resources |

### Access to program source code

| Key Points                                                                                                                                                                                 |                                                                                                                                                                                          |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Access to program source code and associated items (such as designs, specifications, verification plans and validation plans) shall be strictly controlled                                 | Cymmetri's access controls allow appropriate users to authenticate with entitled resources thus ensuring strict controls                                                                 |
| Program source libraries shall not be held in operational systems. The program source code and the program source libraries shall be managed according to established procedures.          | Cymmetri platform is implemented using a containerized deployment standard. This ensures product source code and libraries are not exposed directly to and cannot be changed / modified. |
| IT Support personnel shall not have unrestricted access to program source libraries.                                                                                                       | Cymmetri's access controls allow appropriate users to authenticate with entitled resources thus ensuring strict controls                                                                 |
| The updating of program source libraries and associated items and the issuing of program sources to programmers shall only be performed after appropriate authorization has been received. | Cymmetri platform is a standard product following agile methodology for code changes which adhere to a change management process for any and all changes to the system.                  |
| An audit log shall be maintained of all accesses to program source libraries and program listings shall be held in a secure environment.                                                   | Access to Cymmetri source code and configurations can be restricted through appropriate access policies within the platform.                                                             |



## General Data Protection Regulation (GDPR)

The General Data Protection Regulation (GDPR) imposes strict requirements on organizations that process personal data. This includes specific guidelines related to Identity and Access Management (IAM).

#### General Considerations

* Data Minimization
* Lawful Processing
* Data Subject Rights
* Accountability

#### IAM-Specific Considerations

* **Strong authentication:** Implement strong authentication mechanisms, such as multi-factor authentication (MFA), to protect against unauthorized access.  &#x20;
* **Access control:** Implement robust access control measures to ensure that only authorized individuals can access personal data.
* **Data encryption:** Encrypt personal data both at rest and in transit to protect against unauthorized access and disclosure.
* **Regular reviews:** Conduct regular reviews of access rights to ensure they remain appropriate and necessary.
* **Incident response plan:** Have a plan in place to respond to data breaches and other security incidents.
* **Data retention policies:** Establish clear data retention policies that align with the GDPR's requirements.
* **Consent management:** If relying on consent as a legal basis for processing, ensure that consent is freely given, specific, informed, and unambiguous.

By adhering to these guidelines, organizations can ensure that their IAM practices comply with the GDPR and protect the privacy and rights of individuals.



## Health Insurance Portability and Accountability Act (HIPAA)

The Health Insurance Portability and Accountability Act (HIPAA) sets standards for the privacy and security of Protected Health Information. This includes specific requirements related to Identity and Access Management (IAM).

#### General Considerations

#### Security Rule

* **Administrative safeguards:** Implement administrative procedures to safeguard PHI, including risk assessments, security awareness training, and incident response plans.
* **Physical safeguards:** Implement physical measures to protect PHI, such as access controls, surveillance systems, and disaster recovery plans.
* **Technical safeguards:** Implement technical measures to protect PHI, such as access controls, encryption, and audit trails.
* **Business associate agreements:** If you work with business associates that handle PHI, ensure that they have appropriate safeguards in place and enter into business associate agreements.

#### HIPAA Breach Notification

* **Notify affected individuals:** If a breach of PHI occurs, you must notify affected individuals without undue delay.
* **Report to HHS:** In certain cases, you must also report the breach to the Department of Health and Human Services (HHS).
* **Incident response:** Develop and implement an incident response plan to address security breaches and data breaches.

#### IAM-Specific Considerations

* **Access controls:** Implement robust access controls to ensure that only authorized individuals can access PHI.
* **Authentication:** Require strong authentication methods, such as multi-factor authentication, to prevent unauthorized access.
* **Authorization:** Assign appropriate access privileges based on job functions and roles.
* **Password management:** Implement strong password policies and enforce regular password changes.
* **Data encryption:** Encrypt PHI both at rest and in transit to protect against unauthorized access and disclosure.
* **Audit trails:** Maintain audit trails to track access to PHI and identify potential security breaches.
* **Risk assessments:** Conduct regular risk assessments to identify potential vulnerabilities and take appropriate measures to mitigate them.

By adhering to these guidelines, organizations can ensure that their IAM practices comply with HIPAA and protect the privacy and security of PHI.



## Sarbanes-Oxley Act (SOX)

The Sarbanes-Oxley Act (SOX) is a U.S. federal law that sets standards for financial reporting and corporate governance. While it doesn't explicitly mention Identity and Access Management (IAM), its focus on internal controls and financial reporting has significant implications for IAM practices.

#### Internal Controls

* **Segregation of duties:** Ensure that there is a separation of duties to prevent conflicts of interest and fraud. For example, individuals who have access to create or modify records should not also have the authority to approve or authorize transactions.
* **Access logs:** Maintain detailed access logs to track user activity and identify unauthorized access.
* **Change management:** Implement a formal change management process to review and approve changes to systems and access controls.
* **Regular reviews:** Conduct regular reviews of access rights to ensure they remain appropriate and necessary.
* **Incident response:** Have a plan in place to respond to security breaches and other incidents.

#### Financial Reporting

* **Accurate and reliable data:** Ensure that financial data is accurate and reliable by implementing appropriate access controls and data integrity measures.
* **Management oversight:** Management should oversee IAM practices and ensure that they are effective in preventing unauthorized access and data manipulation.
* **Documentation:** Document IAM policies and procedures to demonstrate compliance with SOX requirements.

#### IAM Specific Considerations

* **User provisioning and deprovisioning:** Establish clear procedures for adding and removing users from systems, ensuring that access is granted and revoked promptly.
* **Password management:** Implement strong password policies and enforce regular password changes.
* **Privilege escalation:** Limit the ability of users to escalate their privileges, preventing unauthorized access to sensitive systems or data.
* **Monitoring and alerting:** Implement monitoring and alerting systems to detect unusual activity or potential security threats.
* **Third-party access:** If you work with third-party vendors or contractors, ensure that they have appropriate safeguards in place to protect your data.

By adhering to these guidelines, organizations can demonstrate compliance with SOX and strengthen their internal controls related to identity and access management.

## Payment Card Industry Data Security Standard (PCI DSS)

The Payment Card Industry Data Security Standard (PCI DSS) outlines requirements for organizations that handle cardholder data. This includes specific guidelines related to Identity and Access Management (IAM). Here are some key points to consider:

#### Requirement 7: Restrict Access to Cardholder Data

* **Assign unique IDs:** Assign unique identifiers to each person with authorized access to cardholder data.
* **Limit access:** Restrict access to cardholder data to only those individuals who need it to perform their job functions.
* **Regular reviews:** Conduct regular reviews of access rights to ensure they remain appropriate and necessary.
* **Least privilege principle:** Grant individuals only the minimum privileges necessary to perform their job functions.

#### Requirement 8: Unique IDs for System Components

* **Identify components:** Assign unique identifiers to all system components that process, store, or transmit cardholder data.
* **Track access:** Track access to system components to identify unauthorized access.

#### Requirement 9: Restrict Physical Access to Cardholder Data

* **Secure areas:** Restrict physical access to areas where cardholder data is processed, stored, or transmitted.
* **Access controls:** Implement physical access controls, such as locked doors and security cameras.

#### Requirement 10: Track and Monitor All Access to Network Resources and Cardholder Data

* **Access logs:** Maintain detailed access logs to track user activity and identify unauthorized access.
* **Monitoring:** Implement monitoring systems to detect unusual activity or potential security threats.
* **Alerting:** Configure alerts to notify appropriate personnel of suspicious activity.

#### Requirement 12: Maintain a Strong Access Control Mechanism

* **Password policies:** Implement strong password policies, including minimum length, complexity requirements, and regular password changes.
* **Authentication:** Require strong authentication methods, such as multi-factor authentication.
* **Privilege escalation:** Limit the ability of users to escalate their privileges, preventing unauthorized access to sensitive systems or data.

#### Requirement 13: Regularly Test Access Controls

* **Penetration testing:** Conduct regular penetration testing to identify vulnerabilities in access controls.
* **Vulnerability scanning:** Use vulnerability scanning tools to identify and address security weaknesses.

By adhering to these guidelines, organizations can demonstrate compliance with PCI DSS and protect cardholder data from unauthorized access.
