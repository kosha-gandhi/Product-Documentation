# 360 Degree Recon

The 360 Degree Recon is one of a type feature of Cymmetri that enables administrators to have a holistic view of user data.

The 360-degree reconciliation process in Cymmetri is designed to ensure that identity data across different systems is consistent and up-to-date. The reconciliation process involves comparing records from Cymmetri with the records in target systems (like Active Directory) and identifying discrepancies that need to be addressed.

The 360-degree reconciliation process in Cymmetri is crucial for maintaining data integrity across all connected systems. By regularly running reconciliation, organizations can ensure that their identity data is accurate.

### Configuring 360 Degree Recon

The 360 degree recon can be configured for all the provisioning applications supported by Cymmetri. Here we will be seeing an example of 360 Degree Recon with Active Directory.

As the first step for configuring 360 Recon the administrator needs to configure a pull recon as explained [here](../provisioning-how-to/active-directory-legacy-provisioning.md#pull-reconciliation).&#x20;

<figure><img src="../../../.gitbook/assets/image (890).png" alt=""><figcaption></figcaption></figure>

Once the pull recon is configured the user next needs to go on the 360 Degree Recon page as shown below:

<figure><img src="../../../.gitbook/assets/image (891).png" alt=""><figcaption></figcaption></figure>

The 360-Degree Reconciliation page displays all the pull reconciliations configured for either users or groups. The administrator can select a configured reconciliation and run a 360-degree reconciliation for that specific pull.

<figure><img src="../../../.gitbook/assets/image (892).png" alt=""><figcaption></figcaption></figure>

Once the 360-degree reconciliation is started the administrator can then go to the History tab and view the results of the reconciliation on the reconciliation dashboard

<figure><img src="../../../.gitbook/assets/image (893).png" alt=""><figcaption></figcaption></figure>

**Reconciliation Dashboard**

The reconciliation dashboard provides an overview of the latest reconciliation run, including key metrics and visualizations to help administrators quickly identify and address issues.

**Key Metrics:**

* **Last Start Date**: Indicates the start time of the most recent reconciliation run.
* **Last End Date**: Indicates the end time of the most recent reconciliation run.
* **Total Processed Records**: The total number of records processed during the reconciliation.
* **Records Pulled from Target App**: The number of records pulled from the target application (e.g., Active Directory).
* **Present in Cymmetri only**: Number of records that exist in Cymmetri but not in the target system.
* **Present in Target only**: Number of records that exist in the target system but not in Cymmetri.
* **Accounts Overdue in the target**: Number of accounts that are overdue in the target system but not reflected in Cymmetri.

**Break Type Analysis**

The break type analysis section uses a pie chart to categorize the types of breaks (discrepancies) identified during the reconciliation. In the example shown in the image, all breaks are categorized as "Present in Cymmetri only," indicating that certain records exist in Cymmetri but are missing from the target system.

**Filter Options**

Administrators can filter the results based on several criteria:

* **Login ID**: Search for discrepancies related to specific user logins.
* **Break Type**: Filter the results based on the type of break (e.g., "IDM exists, Target not exists").
* **Break Count Min/Max**: Filter based on the minimum and maximum break counts.

**Reconciliation Results Table**

The results table provides detailed information on the discrepancies found during the reconciliation process.

**Columns:**

* **User Login**: The login ID of the user in the Cymmetri IDM system.
* **Source Application Login**: The corresponding login ID in the source application (e.g., Active Directory).
* **Application Login**: The login ID in the application (if applicable).
* **Break Type**: Describes the nature of the discrepancy (e.g., "IDM exists, Target not exists").
* **Break Count**: Indicates how many times this particular break type was found for the user.
* **Actions**: Provides option for viewing the user details for further understanding of the user data

**Common Break Types**

* **IDM Exists, Target Not Exists**: This indicates that the user or identity exists in the Cymmetri IDM system but does not exist in the target system (e.g., Active Directory).
* **Target Exists, IDM Not Exists**: This indicates that the user or identity exists in the target system but does not exist in the Cymmetri IDM system.

**Actions to Resolve Discrepancies**

Once discrepancies are identified, administrators can take the following actions:

* **Manual Review**: Examine the discrepancy details and determine if the record should be updated, deleted, or if the discrepancy can be ignored.
* **Automated Actions**: Depending on the configuration, some discrepancies can be automatically resolved by provisioning or de-provisioning the necessary accounts.
