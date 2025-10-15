# Deprovisioning

Deprovisioning rules in any IAM system define the automated processes for managing the removal or deactivation of user accounts and access privileges when certain conditions are met.&#x20;

These rules play a critical role in ensuring that access rights are promptly revoked when users no longer require them, enhancing security and compliance.

In Cymmetri, to establish deprovisioning rules, navigate to the "Deprovisioning" section within the rules under the User Lifecycle Management module.

<figure><img src="../../../.gitbook/assets/image (563).png" alt=""><figcaption></figcaption></figure>

Deprovisioning configuration includes the following:

1. Deprovisioning the user based on the Status or End Date of the user retrieved from the source system. Additionally, administrators can also choose to define provisioning based on any Hook Rule that provides users with the ability to insert custom logic for deprovisioning event.&#x20;
2. Exclusion Application: This feature enables administrators to specify which applications should be exempt from the deprovisioning event in Cymmetri. Consequently, whenever deprovisioning is initiated, these selected applications will not be removed from a user's access.
3. Grace Period: The grace period allows you to set the number of days before the application is removed from the user's access.
4. Process Allocation Size: It refers to the number of simultaneous threads or parallel processes that Cymmetri allocates for executing the deprovisioning tasks. It determines how many user accounts or access revocations can be processed concurrently.

#### Scheduler&#x20;

In Cymmetri, administrators can create a custom scheduler for a Deprovisioning rule to promptly eliminate unauthorized user access as per a specified timetable. This involves defining the scheduler using a cron expression, activating it, and saving the configured settings.

<figure><img src="../../../.gitbook/assets/image (585).png" alt=""><figcaption></figcaption></figure>

