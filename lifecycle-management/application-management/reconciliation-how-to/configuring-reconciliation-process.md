# Configuring Reconciliation Process

Once the applications have been configured to allow that the end-users have been provisioned into the managed application. We may now start configuring the reconciliation process for an application. The reconciliation process involves identifying the user attributes as stored in the Identity hub (Cymmetri platform) and their attributes as a user or a group account in the managed application; and the ensuring that the synchronization of the user and group accounts takes place either one-way or both ways between the managed application and the Identity hub, to ensure that there no discrepancies in the accounts stored by both the systems.

\
The reconciliation process may follow two strategies -&#x20;

1. **Full Reconciliation** \
   Full reconciliation is typically carried out when the managed application is first introduced into an organization’s Cymmetri platform. This involves ensuring all user accounts (and group accounts, wherever applicable) from the Cymmetri platform, are synchronized with the account information on the managed application. This type of reconciliation often takes a longer time, and is often only used as a one-time activity.
2. **Filtered Reconciliation** \
   The Cymmetri platform and the managed application might lose synchronization due to a number of reasons, including backend changes to the user or group account information on the managed application or failure of communication between the identity platform and the managed application. In such cases, filtered reconciliation is employed on a regular, scheduled basis. This includes filters for a particular set of users, or to choose only the users that have been modified on either platforms, this is known as filtered reconciliation.

Cymmetri platform allows for both types of reconciliation phases, by allowing administrator to define an optional user filter during the reconciliation process.

The reconciliation process involves two major processes:

1. **Pull**\
   In this mechanism, the Cymmetri platform allows for user and group account information to be pulled from the managed application.
2. **Push**\
   In this mechanism, the Cymmetri platform pushes the user and group account information to be pushed to the managed application.

Regardless of the process employed, the configuration for the most part remains the same.\
Let us explore the reconciliation configurations on the Cymmetri Platform:

<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003452401/original/nAuk5a_Og72iXfhNfiw5r7caCFVCJUocvg.png?1649361564" alt=""><figcaption></figcaption></figure>

You may access the reconciliation menu by clicking on the application tile, and then clicking on the “Reconciliation” left-hand side menu.

Proceed to configure by clicking on the “+ Add New” button.

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003452411/original/i1trgAErATCXMp3wWNgX0xj1O75UsfbstA.png?1649361585)

1. **Name:** Refers to the name of the Reconciliation process
2. **Modes:** FILTERED\_RECONCILIATION (Currently the only mode supported by Cymmetri)
3. **Sync Fields:** The field from the user/group’s account information as available on the Cymmetri platform that must be used as a basis to identify the corresponding account on the managed application database.
4. **Source Attributes:** The field from the user/group’s account information as available on the managed application database that must be used as a basis to match with the “Sync fields”.
5. **Status:** Whether to run the reconciliation for Active/Inactive users.
6. **Type:** Some applications allow GROUP reconciliation, but most will have USER reconciliation only.

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003452426/original/ysrgSQu-1XKuNg15KjKCtshF1StHOoPZtw.png?1649361597)

Filled Reconciliation basic configuration looks as above.

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003452436/original/zEr4aQoQB6Ct96gdDTgBcS7YipvE4EXCag.png?1649361608)

### Synchronizing Scenarios and Their Corresponding Outcomes

Let us assume we are synchronizing the Cymmetri Platform with a cloud provider using email or mail attribute as the Sync field. As such users on both platforms having the same email address will be matched/un-matched.

#### Following are the scenarios managed by the Cymmetri platform -&#x20;

1. **User does not exist in Target system & exists in Cymmetri:** \
   This indicates a situation during a pull phase or a push phase, where the user account exists on the Cymmetri platform, but not in the managed application. This typically occurs when the users have been pulled into the Cymmetri platform, but the managed application is yet to be synchronized with these users.
2. **User exists in Cymmetri & Target system:** \
   This indicates a situation during a pull phase or a push phase, where the user account exists on the Cymmetri platform and in the managed application, but they may or may not have the same attributes or the same values of the attributes.&#x20;
3. **User exists in Target system & does not exist in Cymmetri:** \
   This indicates a situation during a pull phase or a push phase, where the user account exists in the managed application database but not on the Cymmetri Identity platform. This typically occurs when the users have been pulled into the managed application through its backend and the users have not been centrally managed through the Cymmetri platform.

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003452439/original/8yCSud6JIuItpwWHr0fiXwDmqV4KW4LGvQ.png?1649361622)

### Conditions Explained:

1. **User does not exist in Target system & exists in Cymmetri:**&#x20;
   1. **PROVISION:** User is created in the target system with the attributes as present in their Cymmetri user profile.
   2. **IGNORE:** User is not modified in either system.
   3. **UPDATE:** Not relevant for this scenario.
   4. **DEPROVISION:** User is removed from the Cymmetri platform to be consistent with the managed application user database.
   5. **UNASSIGN:** Not relevant for this scenario.&#x20;
   6. **ASSIGN:** User is assigned access to this system in Cymmetri, this option may be used in the case of options like JIT being available to generate user profile in the managed application.
   7. **UNLINK:** Not relevant for this scenario.
   8. **LINK:** Not relevant for this scenario.
2. **User exists in Cymmetri & Target system:**&#x20;
   1. **PROVISION:** User is created in the target system with the attributes as present in their Cymmetri user profile.
   2. **IGNORE:** User is not modified in either system.
   3. **UPDATE:** User information from the Cymmetri Identity platform is updated using the account information from the managed application and vice versa.
   4. **DEPROVISION:** Not relevant for this scenario.&#x20;
   5. **UNASSIGN:** Not relevant for this scenario.
   6. **ASSIGN:** User is assigned the managed application on the Cymmetri platform in case they are already not assigned.
   7. **UNLINK:** Not relevant for this scenario.
   8. **LINK:** Not relevant for this scenario.
3. **User exists in Target system & does not exist in Cymmetri:**&#x20;
   1. **PROVISION:** User is created in the Cymmetri Identity platform deployment using the account information from the managed application.
   2. **IGNORE:** User is not modified in either system.
   3. **UPDATE:** Not relevant for this scenario.
   4. **DEPROVISION:** User is removed from the managed application user database.
   5. **UNASSIGN:** Not relevant for this scenario.
   6. **ASSIGN:** Not relevant for this scenario.
   7. **UNLINK:** Not relevant for this scenario.
   8. **LINK:** Not relevant for this scenario.

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003452442/original/wDwT9il4a2dWip56ajmNaEd7nFvXsCF9sw.png?1649361637)

Scheduling the reconciliation process:

1. **Next Execution Date:** \
   This indicates the base date to start the execution date and time of the reconciliation process.
2. **Cron Expression:**\
   This indicates the frequency with which the further reconciliation events will be run. There are 6 fields here - \* \* \* \* \* \* (e.g., 5 15 0 1 8 \*) ; they refer to seconds, minutes, hours, days, months, and year after the first execution date.
