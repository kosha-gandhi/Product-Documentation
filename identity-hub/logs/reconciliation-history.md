# Reconciliation History

The Cymmetri platform provides a centralized view for monitoring and auditing all reconciliation activities under the Audit Logs menu. This functionality offers administrators both a high-level summary and detailed drill-down views of each reconciliation job.

The Reconciliation History table, accessible via Audit Logs → Reconciliation History, has been enhanced to display the key reconciliation summary metrics directly in the table view.

This enhancement allows administrators to quickly assess the health and outcome of each reconciliation run without navigating to a separate detail page. The at-a-glance summary typically includes:

* **Pending Records**: Count of records awaiting processing.
* **Synced Records**: Count of records successfully synchronized (created, updated, or deleted).
* **Error Records**: Count of records that failed during the synchronization process.
* **Total Records**: The total number of records processed or considered in the run.

<figure><img src="../../.gitbook/assets/unknown (173).png" alt=""><figcaption></figcaption></figure>

#### Detailed Reconciliation View (View History)

For a deeper analysis of a specific reconciliation run, administrators can select the View History option. This detailed view provides granular data organized across several key categories:

| **Modes**      | Sync field, Source attribute, Job completion time             | Specifies the primary attribute used for matching records, the source attribute used for data, and the final timestamp of the job's completion. |
| -------------- | ------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| **Conditions** | User does not exist in the Target System & exists in Cymmetri | Identifies users flagged for provisioning to the target system.                                                                                 |
| <p><br></p>    | User exists in Cymmetri & Target System                       | Identifies users flagged for profile update or validation across both systems.                                                                  |
| <p><br></p>    | User exists in Target System & does not exist in Cymmetri     | Identifies orphaned accounts in the target system, flagged for de-provisioning or review.                                                       |
| **Summary**    | Pending Records, Synced Records, Error Records, Total Records | The final statistical outcome of the reconciliation job.                                                                                        |

<figure><img src="../../.gitbook/assets/unknown (174).png" alt=""><figcaption></figcaption></figure>

### Role Reconciliation Dashboard

The Role Reconciliation Dashboard is a specialized sub-page within the Recon History section dedicated to auditing and managing user role entitlements.

This dashboard provides administrators with the following granular details for each user involved in a role reconciliation activity:

| **Login**            | The unique login identifier of the user.                                                                                                                                    |
| -------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Already Assigned** | The set of roles that the user held before the current reconciliation process was executed.                                                                                 |
| **Fetched**          | The roles for this user that were successfully retrieved from the target application during the reconciliation run.                                                         |
| **Newly Assigned**   | Roles that have been provisioned to the user as a direct result of the reconciliation logic.                                                                                |
| **To Be Removed**    | Roles identified by the reconciliation logic as needing to be revoked from the user's profile.                                                                              |
| **Status**           | The current state of a role assignment, indicating if the role has been removed, is currently under administrator review, or has been confirmed for continued assignment.   |
| **Actions**          | Interactive options allowing the administrator to drill down for further details on the specific role or to initiate a manual action (e.g., overriding the removal status). |

<figure><img src="../../.gitbook/assets/unknown (176).png" alt=""><figcaption></figcaption></figure>

To establish a new reconciliation job, please refer to the dedicated documentation on [Reconciliation Configuration.](../../lifecycle-management/application-management/reconciliation-how-to/)
