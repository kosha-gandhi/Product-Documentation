# Setting up and managing Access Reviews

Cymmetri allows two types of Access Certifications, namely-

* Access Certification Campaign
* Ad-hoc Certification based on defined events

### Access Campaign                                       &#x20;

* An Identity Governance Campaign is a systematic process of attesting a set of employees who have the appropriate privileges on the appropriate resources at a specific point of time.
* With the help of the campaign, the privileges are revoked when an employee exits from an organization.

### Access Review Menu

Navigate to the Access Review menu by clicking on the Product menu (three dots) and selecting 'Identity Governance'.

<figure><img src="../../.gitbook/assets/image (405).png" alt=""><figcaption></figcaption></figure>

On selecting Identity Governance option the page shown below opens where Existing reviews can be seen as well as new Access Reviews can be added

<figure><img src="../../.gitbook/assets/image (554).png" alt=""><figcaption></figcaption></figure>

#### Steps for creating a Campaign:

#### Campaign Details &#x20;

Click on Add New to create a Campaign and steps for creation is shown as below :<br>

<figure><img src="../../.gitbook/assets/image (811).png" alt=""><figcaption></figcaption></figure>

1. Organization Admin User logs into Cymmetri.
2. The user needs to be an Organization administrator to configure an access review campaign&#x20;
3. The Organization administrator fills in the following fields to start the campaign
   * Name of the Campaign.
   * Certification completion( period in days) - The overall duration of the access review cycle.
   * Pending notification waiting period - A reminder mail is sent if the access review is not done by the approver within defined calendar days.&#x20;
   * Campaign Manager - The person responsible for the overall campaign.
   * Revoke access for pending review tasks ( check box ) - It provides us an option to either revoke or continue  the access of all users if the access review is not completed in a defined timeline.
   * Next Execution Date-  Two options to select from
     * Start Date - Ad-hoc date of execution of campaign
     * Cron Expression - System scheduler to automatically execute the campaign.
4. Save the details of the page.&#x20;

#### Access Review Execution Configuration

Cymmetri provides the ability to define the campaign execution parameters such as one-time / ad-hoc execution or based on a scheduled job from the system (by using the cron expression builder)

<figure><img src="../../.gitbook/assets/image (909).png" alt=""><figcaption></figcaption></figure>

#### Scope

The user fills in the following fields for defining the scope for the certification&#x20;

1. Who does this campaign apply to
   * All users
   * To specific organization groups, users, user types, risks & applications&#x20;
2. Exclusion User - To exclude the user to not be a part of the review process
3. Save the details.&#x20;

All users

<figure><img src="../../.gitbook/assets/image (406).png" alt=""><figcaption></figcaption></figure>

To specific organization groups, users, user types, risk & applications&#x20;

<figure><img src="../../.gitbook/assets/image (999).png" alt=""><figcaption></figcaption></figure>

#### Access Review based on User Type&#x20;

As shown above access review can be configured on various parameters like specific users, specific groups, specific applications and also specific user types. The review based on usertype is one of the crucial way to implement access review, as it enables organizations to review critical user types like service accounts, privileged accounts, and generic accounts.

In Cymmetri, we can perform the access review based on the user type attribute:

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdXfK4Zx4ep_ad-d8iZnynFr4W1ficoR_Joh95ZBb2zSER2Pq79IGRT9Y9IjkMutieXV_BHFh7bEoAlaxx9Bo1dM51j-WBgeKc0oLF_D3PaFISVOJ63dO05-gQ6rWvKAsXdu9d9EvdHOS8oDC5vflSMqJ3_7U6xf8XLnEwmmS8_5Oph1VBXJpw?key=ES3-gdOFgPh8dn0zAQKG8w" alt=""><figcaption></figcaption></figure>

Based on the campaign configuration, the approving authority will be able to approve the access for service accounts, privileged accounts, generic accounts such as common support accounts, etc.&#x20;

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXcoDtnSPECj7i_3nOD9bpeWlS9xDcGiQYqQg3jvYQkVE2Hnv9Cb8Ws0EIABBjSL_O7xp7amKQ7w_9JGWKCN5ADZxjzhh_F4SiMfhw-PP1q4GRX-mFMta1Dh_mCzED9-rgX2Iam79xK8LRiNkhyVgWrbFEC0EO-NnBw8EcAWiRIP05-9lTzirw?key=ES3-gdOFgPh8dn0zAQKG8w" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXflwa4VtQs0ZWAuPYrTBXq7Ews1q62PUr-JwKJAR0fvIf2HpDIBPsLfVm9bkNrYEjVePkPV0YXslh_fNzpKIqs966JMQwzGq2q3V2JH9NqqSeUrfQ-Zh22-E66zxjeEay0kZ6miAH6DfZSMn3yd2k7YJ9dh4c-WdyFtwcAiAG92lPTJumeLyA?key=ES3-gdOFgPh8dn0zAQKG8w" alt=""><figcaption></figcaption></figure>

#### Approval Stages

* The user can set up the approver in three stages
* The user selects the number of approval levels from the dropdown field to select total stages:
* The following fields are displayed after the user selects level approval process:
  * Name: name of the stage
  * Description: further details about the stage
  * Level one approval ( Radio button )
    * User - to specify a fixed approval user
    * Reporting Manager - to specify the reporting manager of the user who is under review
    * Annotations - when a selected annotation does not match, the Campaign Manager will act as the campaign reviewer
* The User fills them and saves the details.

<figure><img src="../../.gitbook/assets/image (814).png" alt=""><figcaption></figcaption></figure>

Similarly Stage 2 Approver and Stage 3 Approvers can also be configured

<figure><img src="../../.gitbook/assets/image (815).png" alt=""><figcaption></figcaption></figure>

### Manage Campaigns&#x20;

* The configured campaign will be displayed under the access review tab in the draft state&#x20;
* For each campaign admin user can:&#x20;
  * View Campaign
  * Edit Campaign
  * Run Campaign
  * Delete the Campaign
* Now Admin can Publish the Campaign and the status of Campaign will change from Draft Status →  Published Status
* Next the Admin can run the campaign manually or based on scheduled jobs.

<figure><img src="../../.gitbook/assets/image (816).png" alt=""><figcaption></figcaption></figure>

### Campaign History&#x20;

* This page shows the Access review history that helps the administrator to track various certification metrics across campaigns.
* It is the Iterations of the campaign performed based on Cron Jobs or when the Administrator runs the campaign.&#x20;
* Administrator can click on the view button to further see details about each user and their access

<figure><img src="../../.gitbook/assets/image (810).png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84017912883/original/dj1OLDqW4CCmtMD_iU44ze4HAPV9KsESfA.png?1666180050" alt=""><figcaption></figcaption></figure>

### Access Review&#x20;

This section provides users with the ability to comprehensively review campaigns. Users can not only assess the campaign at hand but also explore completed reviews and specifically identify those where the user serves as a Campaign Manager.Access Review is available at **My Workspace->Access Reviews->Identity Governance.** Within the Access Review module, users are presented with three distinctive sections:

#### **Active Access Review:**&#x20;

In this section, the approving authority can choose any active campaign for certification purposes. This feature allows for focused attention on ongoing campaigns, streamlining the certification process.

<figure><img src="../../.gitbook/assets/image (550).png" alt=""><figcaption></figcaption></figure>

#### **Completed Access Review:**

Here, users can access a consolidated view of all completed reviews. This section offers a comprehensive overview of the finalized assessments, facilitating efficient tracking and reference.

<figure><img src="../../.gitbook/assets/image (551).png" alt=""><figcaption></figcaption></figure>

#### **Managed Access Review:**

1. Specifically tailored for Campaign Managers, this section showcases all reviews where the user holds the role of a campaign manager.&#x20;
2.  This targeted view enables quick identification and management of campaigns under the user's purview, enhancing overall accessibility and control.

    <figure><img src="../../.gitbook/assets/image (552).png" alt=""><figcaption></figcaption></figure>
3. The Manager can also reassign the review task to another user (say a manager or supervisor) in case the assigned reviewer is not available due to various unforeseen reasons

<figure><img src="../../.gitbook/assets/image (817).png" alt=""><figcaption></figcaption></figure>

### Approver Stage

* While the Campaign is running, the system automatically calculates who is the approving authority, how many user’s access are required to be reviewed in Cymmetri.
* All active campaigns are visible to the Approving Authority.
  *   &#x20; When clicked on  Continue →  List of user’s and their access are shown.

      <figure><img src="../../.gitbook/assets/image (553).png" alt=""><figcaption></figcaption></figure>
* Approver User can then Approve the individual record or in bulk.&#x20;
* In case of revoke access, the system will trigger the selected user for deprovision from the selected application.
*   In case the number of records to review are large in number the approver may filter the records based on various criteria like user, application, device.

    <figure><img src="../../.gitbook/assets/image (809).png" alt=""><figcaption></figcaption></figure>
* The approver can view the user's risk before approving the users access which enables the approver to make informed decisions based on these risk values.

<figure><img src="../../.gitbook/assets/image (719).png" alt=""><figcaption></figcaption></figure>

* Access review and approval for privileged users is very critical and these users can be identified by seeing users with higher score as shown here:

<figure><img src="../../.gitbook/assets/image (93).png" alt=""><figcaption></figcaption></figure>

#### Violations view

* If the user under review has any policy violations, the approving authority will be able to view the same. For details, the approver user can view the violations by clicking on the details button

<figure><img src="../../.gitbook/assets/image (932).png" alt=""><figcaption></figcaption></figure>

The approver user can view the policy violations (if any) under the Violations tab of the pop-up.

<figure><img src="../../.gitbook/assets/image (930).png" alt=""><figcaption></figcaption></figure>

There may be multiple violations of the user based on the [policy configurations of Cymmetri IGA](../compliance-management/iga-policy-violations.md).&#x20;

#### Certification History&#x20;

* The approver user can view the past certification history for the current user by clicking on the history button.&#x20;

<figure><img src="../../.gitbook/assets/image (934).png" alt=""><figcaption></figcaption></figure>

For a comprehensive view of the user's events pertaining to the campaign, the approver user has the ability to view the Audit events under the Audit Log tab of the detials pop-up.

<figure><img src="../../.gitbook/assets/image (933).png" alt=""><figcaption></figcaption></figure>

### Filtering Reviews

Access Reviews provide easy filtering of review records based on following types:&#x20;

* User
* Application
* Role
* Privileged Device
* Custom Attribute

The images below shows each type of filter.

#### Filter by users

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXeka9To10kWYNUk_AGD4_HTwoE8f55z2ZtprvfthXB0nzkjOsoTyi5YHd2ZCMrhbOKj9ZYncwvDkFqzbrHujkRY2l-h2ZOFgjK4Mc7vt7LQoHz6OncZS2Vz8anTv8667aDx9L1jETWIsbMxGOLWIVAXr8BG6wuZ65hJMz3BUnUPnEZP6UmP4ZQ?key=ES3-gdOFgPh8dn0zAQKG8w" alt=""><figcaption></figcaption></figure>

#### Filter by Roles / Entitlements

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXeQwxUoTDq7i4_ObDd3ViVh_8mfnb9OpmIdY10enMPlX0Khq78DVVMxK7iu2z5WGNIAhmYcHw7DZj46-7l74zF88oX_WX-Z1x4f2rU4i05EA7ElVlW8ocsENs99w7j14oDPTibAHOhiIzHFBkYtJBaV7IOw9EdKEGtZ9UJ_WIX-GSQilYV1rQM?key=ES3-gdOFgPh8dn0zAQKG8w" alt=""><figcaption></figcaption></figure>

#### Filter by Custom Attributes&#x20;

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXcBm4BK-qvxzTrmvIMVL9t3Tx63_VxRn6qQXXj3yPOlfQw1rDWH2J07vwTzn4rYfX2EU5jKfxfiBNsxTrDX6JuUaJtVvkT837mdw9tFkogIcBwRuVbHAU7k304VQ6MNlGvmwWgRpfsjApIqkYE-cmVTlGNF5WvcGFjo8UKpmrMBq15NXsXiYR0?key=ES3-gdOFgPh8dn0zAQKG8w" alt=""><figcaption></figcaption></figure>

### Access Review Scope

Cymmetri provides ability to define the scope of the campaign based on several criteria. Primarily, the campaign can be run for all the users or restricted to&#x20;

* a set of users,&#x20;
* a set of groups,&#x20;
* a set of applications,&#x20;
* based on risk categories,&#x20;
* based on user type

Within user category, there may be other filters that can be applied to restrict the campaign scope

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXckZ9j_M1EXesq7gdsV4JyDK9JrwP9e_rTcDw6fo0TK5BoGuVIRGolHA86Pr9J-rX4iyu-UBArOjD2eQfU6JyB9B4xdgWWrPa-NTo5Iox_bjuUXMejJaD2PRDAJ-PlgZW8Y_p--LVnpshuwWiZUTc2mitel8qGWym_3UC9sdJmWHkcKwjXHKg?key=ES3-gdOFgPh8dn0zAQKG8w" alt=""><figcaption></figcaption></figure>

Group based filtering

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXf3D7FpsIC7MPam1CazMJHVnvKoO6u2_pN7BQEheFp0gmrVTpOZyjnLrRlnRsVMylQKZxigz7zh0yVN2oXRQhffHqrwrwVWkQ8dTyyPNrM-HHumN9KQ5Lm2lYfjLcrhUPaeiWAYitVa6r5kwParC4kPrASpVJzExV32ejHi_aB5JUoNkQQMYJQ?key=ES3-gdOFgPh8dn0zAQKG8w" alt=""><figcaption></figcaption></figure>

Risk based filtering-

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXf4spbaeGcnjQO7wj18nf1wMWnHWmO2NYFAzrjPA7xe3knV7XoX2zBYfUuZoWfJM7e_7WA2yH1V4_4-HKivD6MNL4NpMPKzKJkR5Z8PGqFfGnjer62fJR5jdRKJfuoKrMVnQPld6LO9TRD_9BNvS4bcHLHv9fDG4B2X3s88DfDxqeRQuTw2Dt0?key=ES3-gdOFgPh8dn0zAQKG8w" alt=""><figcaption></figcaption></figure>

### Campaign Notifications

Reviewers receive periodic email notifications based on the campaign configuration set during the creation of the campaign, reminding them to complete the campaign actions

<figure><img src="../../.gitbook/assets/image (818).png" alt=""><figcaption></figcaption></figure>

### Access changes during and after campaign

* For the users who are marked “Approved”, such users will continue to have access to the resource. If there are multiple stages of approval then all approvers must mark as “approved”
* For the users who are marked “Rejected” at any stage of the campaign, their access will be revoked immediately or unassigned from the application if no remediation workflow is setup. In case of remediation workflow, the user's access to the application shall remain till the relevant approving authority approves or rejects the remediation task. Else, the workflow task will be closed as per the closure policy defined in the remediation workflow.&#x20;
* In case no approval or revocation is done, such users access will either be revoked as per the campaign configuration marked “revoke access for pending”. Else user’s access will continue if no action is taken during campaign period.&#x20;

### Access Review Workflow

Cymmetri allows setting up workflows to process campaign users marked for immediate revocation of access. For this, the workflow needs to be created and corresponding workflow rule must be setup to process remediation of access revocation through the Cymmetri approval process.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXc3knXpsTc54Ny3HurGmZ0GzSBZIn45DAoFEooti6NN2Ifa3XhM_87FeO2qehirWljUbawmoDY3Nl1fNdr8bc9vK-rIrDT83x6HZAk3h7IOnVP7M9PxXLwePzzNOh__bXz4pPwjVRrSiDNIXXxtBPFw6Nu2s3Gr3vyeHRglalf08dTxZmoy3es?key=ES3-gdOFgPh8dn0zAQKG8w" alt=""><figcaption></figcaption></figure>

## Ad-Hoc Certifications

In Cymmetri, certain events can lead to change in Access grants for users. These events may require a careful review of the changing rights for such users. As an example, the location of a user updates from the source of truth system / HRMS, in which case Cymmetri will change the relevant location attribute for the user triggering a change in a access in integrated target applications. As a policy, the organization may require such changes to be approved / verified by relevant approvers.&#x20;

Cymmetri allows a concept of continuous certification where the reporting manager of a user gets alerted of the changing roles and access in target applications. The reporting manager will get a view of all the relevant access grants for all the reportees and the manager, if allowed as per Cymmetri configuration, can unassign a role or remove an application's access for such users as they deem not required.&#x20;

<figure><img src="../../.gitbook/assets/image (85).png" alt=""><figcaption><p>Artefact - A Reporting manager's view of a reportees Risk &#x26; Violations</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (86).png" alt=""><figcaption><p>Artefact - Reporting manager removing role for a reportee</p></figcaption></figure>

In the above artefact example, once the reporting manager removes the role, based on the Cymmetri configuration, the role will be unassigned if there is no approval workflow attached with such an event.&#x20;

Similar to the manager performing the ad-hoc certification process, Cymmetri can be configured to automatically raise tasks for access approval in case of events such as transfer of user, update to any of the HRMS attributes which affect the roles assigned to the user, etc.&#x20;

## Pre-requisites and Assumptions

* Users must be present in Cymmetri and assigned to applications (with or without roles)
* Approving Authority i.e  Manager should be present in the system, if not present then all the user's list pending for approvals will go to the Campaign manager.&#x20;
* The Applications selected for the Campaign must be Integrated for Provisioning and Deprovisioning, if not integrated then for the particular user, system will merely unlink the application for user.&#x20;
