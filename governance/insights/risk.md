# Risk

Risk assessment of users in Cymmetri involves evaluating the potential risks associated with user access and actions within the Cymmetri platform. This assessment helps in identifying and mitigating risks to ensure the security and integrity of the system.

The risk calculations are done based on various Cymmetri and AD metrics. A list of these metrics can be seen here:

Cymmetri offers in-depth insights into user risks. To view this information, navigate to **Insights > Risks.**

### Risk Scoring

Cymmetri allows **Aggregate Risk Scoring** to offer a holistic view of security risks across various organizational levels, such as by manager, department, location, or company-wide. Below is a structured approach to profiling and organizing these risk scores:

### 1. Risk Aggregation Overview

* **Risk Score Calculation**: The solution must aggregate individual user and role-based risks to produce higher-level risk scores that reflect the overall security posture across different tiers of the organization.
* **Formula**: Risk scores can be calculated using weighted factors such as:
  * Severity of risks (e.g., High, Medium, Low)
  * Number of violations
  * Impact on critical business applications

### 2. Profiled Risk Scores

The system should generate reports that profile risks across several organizational dimensions:

#### a. By Manager

* **Manager Name**: Identify managers overseeing specific users or teams.
* **Team Risk Score**: Aggregate risk score for the manager’s team, considering users' access rights, policy violations, SoD violations, and role mismanagement.
* **Manager’s Accountability**: Identify potential risks related to the manager’s own access and their team's overall risk exposure.
* **Top Risks by Team**: Highlight the most critical risks faced by each manager’s team.

#### b. By Department

* **Department Name**: Clearly identify departments (e.g., Finance, HR, IT).
* **Department Risk Score**: Aggregate risk for the entire department by analyzing access patterns, policy violations, and SoD conflicts among members.
* **Risk Breakdown**:
  * Percentage of High, Medium, and Low risks by department
  * Number of roles and permissions posing risks within the department
  * Key Applications at Risk: Applications within the department that are highly exposed to security threats

#### c. By Location

* **Location Name**: Identify office locations or regions where users are based.
* **Location Risk Score**: Aggregate risk based on geographic considerations, accounting for localized compliance and security issues.
* **Risk Distribution**: Display geographic risk scores to indicate which locations have the highest or lowest security vulnerabilities.

#### d. Company-Wide

* **Overall Risk Score**: Present a high-level, company-wide risk score reflecting the organization’s overall security posture.
* **Company-wide Risk Distribution**:
  * Total number of high, medium, and low risks across the company
  * Key risk contributors (departments, managers, locations)
  * Top 10 Critical Risks: Highlight the most urgent risks requiring immediate attention
  * Historical Trend: Display changes in the company-wide risk score over time, such as improvements post-policy enforcement or increases due to new vulnerabilities.

### 3. Risk Severity and Prioritization

* **Severity Levels**: Each profiled risk should be categorized as:
  * **High Risk**: Critical and requires immediate remediation.
  * **Medium Risk**: Significant but less urgent.
  * **Low Risk**: Monitor, but not immediately critical.
* **Prioritization**: Focus on departments or teams with higher aggregate risks for expedited action.

### 4. Risk Mitigation Recommendations

For each profiled risk, provide:

* **Mitigation Actions**: Suggestions to reduce the risk (e.g., removing unnecessary roles, enabling multi-factor authentication).
* **Responsible Entity**: Identify who (manager, department, or location) should take action to resolve the risk.
* **Remediation Deadline**: Suggested deadlines for risk mitigation.

### 5. Dashboard and Visualization

The IAM solution should feature a dashboard to visualize aggregate risk scores across the organization. Key dashboard features should include:

* **Heat Maps**: Color-coded maps displaying risk scores by location, department, or manager.
* **Bar Charts and Graphs**: Visual representation of risk distribution and trends over time.
* **Filter Options**: Allow users to filter views by department, location, manager, or specific applications for detailed analysis.

### 6. Periodic Reporting

* **Report Scheduling**: Automatically generate and distribute risk score reports at regular intervals (e.g., monthly, quarterly).
* **Stakeholder Distribution**: Tailor reports for managers, department heads, compliance officers, and the CISO, based on their level of responsibility.

### 7. Integration with Governance and Compliance

* **Compliance Checks**: Align risk scoring with compliance frameworks (e.g., SOX, GDPR, HIPAA) to highlight areas where the organization may be falling short of regulatory requirements.
* **Audit Trail**: Provide detailed logs of risk score changes, access adjustments, and mitigation actions for audit purposes.

Cymmetri's Risk scoring offers both a detailed and high-level overview of security risks, empowering stakeholders to make informed decisions and prioritize security efforts across the organization.

### Dashboard

The **Dashboard** section provides a comprehensive overview of the current risk status across the Cymmetri platform. By visualizing key metrics and trends, it allows for quick identification of high-risk areas and users.&#x20;

#### Risk Stats&#x20;

The dashboard features a "Risk Stats" section, presenting a graphical display of the number of users categorized by risk level—High, Medium, and Low. This visualization represents data synced across various days within a specified date range.

<figure><img src="../../.gitbook/assets/image (127).png" alt=""><figcaption></figcaption></figure>

It also shows a section where it shows various risk calculation metrics. This section outlines various user activities and status changes observed over the past 7 days, as well as upcoming account expirations in the next 30 days.&#x20;

* **User cannot change the password in AD:** Users that are restricted from changing their passwords, which could affect user security and compliance.
* **User Recently Created last 7 days:** New user accounts have been created in last 7 days.
* **User Recently Modified last 7 days:** Accounts that have been modified in last 7 days in any ways.&#x20;
* **User Recently Deleted last 7 days:** Users whose accounts that have been removed  in last 7 days. Monitoring deletions is crucial for understanding changes in user access and potential security risks.
* **User Account Expires next 30 days:** Users whose accounts are set to expire within the next 30 days. These need to be reviewed to determine if extensions are necessary.
* **User recently not logged in last 7 days:** Users whose accounts that have not had any login activity in the last 7 days. This could indicate unused accounts or potential issues with user access.
*   **User recently locked last 7 days:** Users whose accounts that have been locked out due to incorrect password attempts or other security protocols in the last 7 days.

    <figure><img src="../../.gitbook/assets/image (128).png" alt=""><figcaption></figcaption></figure>

Each of these section has a **View** link which opens up a modal that further shows user details for each of these metrics as shown below:

<figure><img src="../../.gitbook/assets/image (129).png" alt=""><figcaption></figcaption></figure>

### Risk Configuration

The risk configuration section is used to configure Active Directory which is later used to sync Active DIrectory risk parameters.&#x20;

<figure><img src="../../.gitbook/assets/image (130).png" alt=""><figcaption></figcaption></figure>

Some of the basic configurations fields are:

* **Name:** Risk Configuration Name. _For eg. AD Risk Config_
* **Description:** A general description about the Risk Comfiguration
* **IdM Repository Field:** A unique identifier on Cymmetri side. _For eg. login_
* **Source Attribute Name:** A unique identifier from Active Directory. _For eg. sAMAccountName_

Next we need to do User and Server Configuration

#### **Server Configuration**

Consists of configuring the connector server. Enter the IP address of the host server and its password. The rest of the fields come pre-filled with default values; you can change them according to your use case.  Next, click on the save configuration button.&#x20;

Mentioned below are the field descriptions:

| Field Name               | Description                                     |
| ------------------------ | ----------------------------------------------- |
| Host server              | The IP address of the host server               |
| Server port              | Port of the host server                         |
| Server Password          | Host Server password                            |
| Server Connector Timeout | Timeout of the connector server in milliseconds |
| Server Connector UseSSL  | Connector server SSL configuration              |

_Note: Ensure that the bundle used is for Active Directory Risk configuration is **adanalytics-1.0-bundle.jar** and the connector server version is atleast **1.5.2.0**_

<figure><img src="../../.gitbook/assets/image (131).png" alt=""><figcaption></figcaption></figure>

#### User Configuration

User Configuration consists of all user settings like domain name, search filter, etc. We can also configure an OU (Organisational Unit) in this window. &#x20;

<figure><img src="../../.gitbook/assets/image (133).png" alt=""><figcaption></figcaption></figure>



| Field Name                           | Description                                                                                                                                                                                                         |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Entry object classes                 | Object classes to which the Account class is mapped                                                                                                                                                                 |
| Base contexts to synchronize         | Display names used for Active Directory synchronisation to Cymmetri, such as domain controller name                                                                                                                 |
| Credentials                          | Admin password to connect to Active Directory                                                                                                                                                                       |
| Default id Attribute                 | Default attribute Id                                                                                                                                                                                                |
| Failover                             | An array of LDAP URLs specifying failover servers. If the connector cannot make a connection to the server specified in the host property, it will try connecting to these failover servers in the specified order. |
| Custom user search filter            | Search filter used to search accounts                                                                                                                                                                               |
| Default people container             | Default people container can be used during create operation in case of entry DisplayName is not explicitly mentioned                                                                                               |
| Host Server                          | Active Directory server hostname that would connect to Cymmetri                                                                                                                                                     |
| Object classes to synchronize        | User object classes to synchronize. The connector ignores any changes if it cannot find modified entry object classes in this property.                                                                             |
| Page size                            | Get users from Active Directory with the provided size                                                                                                                                                              |
| Pageable result                      | Get users from Active Directory with the provided size pageable result                                                                                                                                              |
| Server port                          | Port of the Active Directory connector server                                                                                                                                                                       |
| Principal                            | Admin username of the Active Directory                                                                                                                                                                              |
| Retrieve deleted users               | Indicate if deleted users must be synchronised also.                                                                                                                                                                |
| Server Connector UseSSL              | Connector server SSL configuration                                                                                                                                                                                  |
| Trust all certs                      | Indicative if all server certificates can be trusted                                                                                                                                                                |
| UID attribute                        | Unique Identifier Attribute                                                                                                                                                                                         |
| Base context for user entry searches | Display the Name of OU (Organization Unit), Root domain or Root controller required for user entry search                                                                                                           |
| User search scope                    | The scope could be a subtree or object for user search                                                                                                                                                              |

### Risk Assessment History

The section allows administrators to view a list of synchronization events that have occurred for Active Directory (AD) Risk Details, along with the ability to access a detailed Risk Assessment Report for high-risk users.

The Risk Assessment History page displays a list of synchronization events for AD Risk Details. The following information is displayed for each synchronization event:

* **Name:** The name of the synchronization event.
* **Description:** A brief description of the synchronization event.
* **Start at:** The start time of the synchronization event.
* **End at:** The end time of the synchronization event.
* **Start Mode:** The start mode of the synchronization event (MANUAL or AUTO).&#x20;
* **End Mode:** The end mode of the synchronization event (MANUAL or AUTO).
* **Status:** The status of the synchronization event.
* **Actions:** The Actions section contains a View button, which allows users to view the Risk Assessment Report for the synchronization event.

<figure><img src="../../.gitbook/assets/image (427).png" alt=""><figcaption><p>Risk Assessment History</p></figcaption></figure>

**Risk Assessment Report**

The Risk Assessment Report provides detailed information about all users associated with the synchronization event. The following information is displayed for each user:

* **Name:** The name of the user.
* **SAM Account:** The Security Account Manager (SAM) account name of the user.
* **Mail:** The email address of the user.
* **Type:** The type of user.
* **Risk Score:** The risk score assigned to the user.
* **View Risks:**  A View Risks button which allows users to view the Risks for a particular user.

<figure><img src="../../.gitbook/assets/image (428).png" alt=""><figcaption><p>Risk Assessment Report</p></figcaption></figure>

**View Risks Button**

The View Risks button is enabled only for high-risk users and allows administrators to view various AD and Cymmetri metrics used for risk calculation. This button provides additional insight into the factors contributing to the user's high-risk status.

**Risk Details Page**

The Risk Details page displays detailed information about a specific user's risk assessment. The following information is displayed:

* **Sam Account Name:** The Security Account Manager (SAM) account name of the user.
* **Display Name:** The display name of the user.
* **Mail:** The email address of the user.
* **User Type:** The type of user (e.g., Employee).
* **Risk Score:** The risk score assigned to the user.

Additionally, a table is provided that lists the risk type name (ADProcessor or CymmetriUserProcessor), description, and risk score for each risk associated with the user.

<figure><img src="../../.gitbook/assets/image (132).png" alt=""><figcaption></figcaption></figure>

#### Recommendation and Remediation

Cymmetri recommends risk mitigation actions for high risk users, for various actions like monitoring of user activity, review certifications, and remediation of various policy violations

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXce-xeetHZbTw6ZVbNZsy5GP6i3gnKlbjQ3vagmTpwzquIHLSlwecxj4xo0TOIgBMH8PCxlMCxLcyPj11AGVpbTniA8lPNWSW5zCgSEMBgH8ocrQuHFbFYkKlqsPO5TsGGkdILntMXA5HjdWNuzyThStyzSIKyPC9yf33qvUqvzMlzlNOZ-Mw?key=ES3-gdOFgPh8dn0zAQKG8w" alt=""><figcaption></figcaption></figure>

### Defining Risk Parameters

&#x20;Cymmetri provides a framework for managing risk arising for application access to organization users. Broadly, the risk is quantified on the basis of Qualitative and Quantitative measures

### &#x20;Qualitative Risk

This is a risk that is identified from the knowledge of the system. This means that even in absence of the Enterprise Role model or mapping of activities or tasks or processes to the users, a certain risk value may still be assigned to the users, purely based on the application roles based on the COSO framework (i.e. admin / maker / checker / read only) and applications assigned to them.

&#x20;The qualitative risk calculation will be based on:\
• The number of applications assigned to a particular user, the risk associated with the application, &\
• The risk associated with the COSO type of the application role.

### &#x20;Quantitative Risk&#x20;

This is a risk that is identified from the specific classification of application roles based on High, Medium and Low risk. The risk classification is thus based on users having roles assigned to them.

&#x20;To configure the risk parameters, it is necessary to categorize the [application level risk](../../lifecycle-management/application-management/getting-started/application-detail.md#application-risk-level) as well as role level risk.

### Risk Based Certification

Cymmetri enables trigerring of ad-hoc user certification based on parameters as mentioned below:

*   User's current risk level/ score

    <figure><img src="../../.gitbook/assets/image (911).png" alt=""><figcaption></figcaption></figure>
*   Duration between certification cycles

    <figure><img src="../../.gitbook/assets/image (975).png" alt=""><figcaption></figcaption></figure>
* Manual execution of certification task by manager/ admin

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXcSViCy78ZlvvuGoq3fVW64kW6ljxz_J1NlEwx40_MHTo7rZYURc-VXdIu7Ajbi5R0tKErE7YO175dZgYi76M-5LtWr6hLZDxkdM5i-laaxDTP7sJV3oMqUtteXTRSRIJc5_2_a8_UTcGSNbxytJs0q9Ei-9kLfF2iwHgX84d7K0En1-Nf_Cg?key=ES3-gdOFgPh8dn0zAQKG8w" alt=""><figcaption></figcaption></figure>



### Approver View&#x20;

The above mentioned configurations assist the approving / certifying authorities to have a nuanced view of the user, their entitlements and the risks associated as per the existing policy configurations in Cymmetri. Refer the [Access Certification](../access-certification/setting-up-and-managing-access-reviews.md) process for more details.&#x20;



### Risk Based Reports

Considering Cymmetri has the ability to identify the potential risks associated with user identities and their entitlements from the system, the system can thus provide relevant risk assessment.

The parameters influencing the risk measures are several-

* User Profile / High Risk Users
* Application Access Reviews
* Groups assigned to user
* Role assigned to user
* IT Roles provisioned to user
* Policy violations including SoD
* Anomaly Detection

<figure><img src="../../.gitbook/assets/Raw Risk Scores (002).png" alt=""><figcaption></figcaption></figure>

Refer Cymmetri Risk Reporting video

{% file src="../../.gitbook/assets/Reporting Recording.mp4" %}

***

### Risk based Reporting

The Identity and Access Management (IAM) solution generates Defined Security Risks Report by Application with the following core elements:&#x20;

1. **Application Summary**&#x20;

* Application Name
* Application Owner
* User Base

2. **Risk Identification**

* Access Control Risks
* Excessive Privileges
* Unauthorized Access
* Inactive Accounts (dormant access)
* Role and Permission Risks
* Redundant Roles
* Orphaned Roles
* Role Accumulation
* Segregation of Duties (SoD) Violations
* Policy Non-Compliance
* Password Policies
* Multi-Factor Authentication (MFA)
* Compliance Gaps
* Risk Scoring&#x20;

3. **Affected Users**

* Name and Role
* Access Level

4. **Historical Trends**

* Risk Evolution
* Resolved Risks

5. **Recommendations**

* Remediation Actions
* Role optimization or recertification
* Removing excess privileges
* Enforcing stronger password policies or MFA
* Addressing SoD violations through role restructuring
* Deadline for Action

6. **Integration with Incident Management / Service Desk**

* Incident Ticketing
* Status Tracking

7. **Audit Logs**

* Access Changes
* Violation Occurrences

8. **Reports**&#x20;

* Export Options - Excel, PDF, CSV
* Automated Distribution



