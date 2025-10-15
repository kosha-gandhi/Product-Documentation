# Scheduler History

In Cymmetri the "Scheduler History" feature plays a crucial role in maintaining visibility and control over scheduled tasks and operations. This functionality is designed to offer administrators insights into the history of scheduled events, providing transparency, accountability, and efficient management of routine processes.

In the "Scheduler History" tab, accessible within the Logs section of Cymmetri, administrators can delve into the details of scheduled tasks, gaining insights into various aspects of the scheduler's operation. The information presented includes:

Event of the Scheduler: Specifies the type of scheduler event that took place.

1. **Event of the Scheduler:** Specifies the type of scheduler event that took place.
2. **Description:** Provides a brief description of the scheduled task or operation.
3. **Operation Performed on the Scheduled Period:** Outlines the specific action executed during the scheduled period.
4. **Planned At:** Indicates when the scheduler was initially planned or scheduled.
5. **Sub Event:** Offers details about any sub-events associated with the scheduler operation.
6. **Executed At:** Specifies the timestamp when the scheduler was executed.
7. **Execution Status:** Highlights the status of the scheduler execution, indicating whether it was successful or encountered issues.
8. **Remarks (If Any):** Includes any additional remarks or notes related to the scheduler operation, offering insights into the execution process.

<figure><img src="../../.gitbook/assets/image (441).png" alt=""><figcaption></figcaption></figure>

### Failed Jobs

The scheduler history provides various filters to identify status of failed jobs as shown below:

<figure><img src="../../.gitbook/assets/image (912).png" alt=""><figcaption></figcaption></figure>

These failed jobs are sent out as alerts to specified users as per the [notifications template](../../getting-started/personalization/personalize-notification-templates.md)



### Reconciliation History

Reconciliation History provides a centralized dashboard for all system reconciliation jobs in one page. The relevant admin user can view the summary of all the tasks in progress, completed or aborted.&#x20;

<figure><img src="../../.gitbook/assets/image (976).png" alt=""><figcaption></figcaption></figure>

The tasks that have failed can be manually processed to run again by clicking on the retry button next to the failed history.&#x20;

The Reconciliation job will also alert the specified Cymmetri user of the tasks over email. The configuration is two-fold-

1. Global notification
2. Specific application notification

Cymmetri includes the ability to retry failed records based on the failed event. Administrators can configure the maximum number of retry attempts and set up notifications according to these settings.&#x20;

Cymmetri will send the alerts for all job status events to the specified user or email.

<figure><img src="../../.gitbook/assets/image (977).png" alt=""><figcaption></figcaption></figure>

