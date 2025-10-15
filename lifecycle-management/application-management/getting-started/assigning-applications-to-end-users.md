# Assigning Applications to End Users

Once the managed application has been added to your Cymmetri Identity platform tenant, you will be able to assign applications to your end-users.

## Application Assignment

There are three ways in which applications can be assigned to users:

1. Admin may assign an application directly to a user.
2. Admin may map an application to a group; and the user is added to the group or is already part of the group.
3. End User may request an application and is granted access to the application.
4. Bulk Assignment of application to a set of users

Let us understand the flow for each of the above mentioned scenarios:

### 1. Admin assigns an application directly to the end user

Users with admin roles such as Organization Admin, Domain Admin, or Application Admin on the Cymmetri platform can assign managed applications to end-users .

* First, we need to add the application to the Cymmetri platform&#x20;
* Next, we move to configure the application to assign it to an end user.&#x20;
* Click on the application tile to configure it.

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003452584/original/xiYYVZYw6l-DaQrYB5-MfcsEwLWHz_IyTQ.png?1649361741)

The flow for assignment goes as follows -&#x20;

\
\


<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003452593/original/OeB-MQUg9xDm_Lut2kePYwlqqDDAB5vIAA.png?1649361758" alt=""><figcaption><p>Assignment Flow 1</p></figcaption></figure>

**Description:**

1. Admin clicks on the application tile, and starts the configuration.
2.  Click on the Assignments tab on the left hand side menu.\


    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003452599/original/nbuQEr1_YjbmPYpqc7LoRXnv4LSehpVcXA.png?1649361774" alt=""><figcaption></figcaption></figure>
3.  Click on the “Assign New” button on the Users menu.\
    \


    ![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003452608/original/sxN2BHQBNXwusaI7jzq-mioYIrOsOMowfQ.png?1649361803)
4. Search for a user in the search text box, and once the user is found, click on the “Assign” button.\
   \
   ![](<../../../.gitbook/assets/image (321).png>)\

5. Here we need to decide whether we want to provide a Lifetime Access or a Time Based Access
   1. Lifetime Access: Users have access to the application without any time restrictions.
   2. Time Based Access: Users have access to the application only for the specified range of time. We need to provide a Start Date & Time and an End Date & Time for Time Based Access.
6. Now click on Save to register a request for the application assignment. If no Workflow is configured for the said application the application is immediately assigned to the user.
7. If a workflow for application provisioning is configured then the workflow is been initiated.&#x20;
8.  The workflow approver will then receive a request to approve the user assignment in their inbox.

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003452811/original/Tw_Bfj8y-MCIRAw47JHl6ihya55-WB098g.png?1649362021" alt=""><figcaption></figcaption></figure>
9.  Now the approver may approve or reject the user assignment

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003452822/original/k9DcpEWagBvk1GTXFm2hL0CQBfIijv5B0g.png?1649362035" alt=""><figcaption></figcaption></figure>
10. The approver may change the start and end date, if required; refer to the dynamic form attributes passed during the application assignment.
11. To continue the flow click on Accept button.
12. Now the next level of approver will be able to see the previous levels of approval, and similar to the previous level of approval, the approver may change the start and end date, if required; refer to the dynamic form attributes passed during the application assignment.\


    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003452839/original/szqPQHWWV4Dr4usjPr9vApQUe8eOcRHGYQ.png?1649362063" alt=""><figcaption></figcaption></figure>
13. Click “Accept” to proceed.
14. After the last level approver has also approved the assignment, the backend processes will run the application provisioning flow.
15. Once the user has been provisioned in the application, they will be able to see it in their list of applications.

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003452855/original/yIiCVFhX-xmZBLAib632fRt2FOo2gfsddg.png?1649362113)

### 2. Admin assigns an application directly to a group

Users with admin roles, such as Organization Admin, Domain Admin, or Application Admin, in a Cymmetri Identity platform deployment, will have the ability to assign entire groups of users to managed applications.

1. First, we need to add the application to the Cymmetri platform&#x20;
2. Next, we move to configure the application to assign it to a group.&#x20;
3. Click on the application tile to configure it.

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003452871/original/HJ0p2g84Uq3t2iZjw-Njl0f_1F5Xt2NTjA.png?1649362175)

The flow for assigning a group to an application goes as follows:

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003452874/original/jBAmY21QlWvt6p9pYzv_LE5YdAejqJA4hg.png?1649362184)

#### Description:

1. Click on the application tile, and start the configuration.
2. Click on the Assignments tab on the left hand side menu.

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003452877/original/wuX1T9aiREcmEA2Nr79IPjpIDruIl2fDyw.png?1649362194)

&#x20; 3\. Click on the “Assign New” button in the Groups section.

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003452927/original/FyPDfWvkssrdf2fjxUZx23scPYrpHsxboQ.png?1649362230)

4\. Search for the group you wish to assign the application to and click on the assign button.

<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003452938/original/5xNHapIgNY2Oe4HsNYIMNFkOMtl6VOKcBw.png?1649362253" alt="" width="375"><figcaption></figcaption></figure>

5\. Checking for the users who belong to the group, we can see that the application has been assigned.

<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003452940/original/yIQBsDwXIReecmD9CzTG6Jn5PyEkMnuPXA.png?1649362261" alt=""><figcaption></figcaption></figure>

6\. Viewing the application tiles, we can see if the user was directly assigned the application or received access by the virtue of being part of a group.

### 3. User requests for an application

Users on the Cymmetri platform can request access to a managed applications as a Self-Service feature.

The flow for an end-user to request for an application is as follows:

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003452944/original/A7QgI3tEFdKgPlJmwJ6QpDQAqYO3Hw1qVw.png?1649362276)

#### Description:

1. Visit the “My Workspace” menu.
2. Click on the “My Access” left-hand side menu.&#x20;

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003452946/original/9iDRCJViyzRPycWajWXJTO5RleOCaBfiDA.png?1649362286)

3\. Now Click on the “+ Request” button on the top-right button.

<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003452994/original/NJpHoh2kU4Unhqv-CI8trs3K4KwUc4KN9g.png?1649362313" alt=""><figcaption></figcaption></figure>

4\. Click on the Application Icon to start the request process\
\
![](<../../../.gitbook/assets/image (321).png>)\


1. Here we need to decide whether we want to provide a Lifetime Access or a Time Based Access
   1. Lifetime Access: Users have access to the application without any time restrictions.
   2. Time Based Access: Users have access to the application only for the specified range of time. We need to provide a Start Date & Time and an End Date & Time for Time Based Access.
2. Now click on Save to register a request for the application assignment. If no Workflow is configured for the said application the application is immediately assigned to the user.
3. If a workflow for application provisioning is configured then the workflow is been initiated.&#x20;
4.  The workflow approver will then receive a request to approve the user assignment in their inbox.

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003452811/original/Tw_Bfj8y-MCIRAw47JHl6ihya55-WB098g.png?1649362021" alt=""><figcaption></figcaption></figure>
5.  Now the approver may approve or reject the user assignment

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003452822/original/k9DcpEWagBvk1GTXFm2hL0CQBfIijv5B0g.png?1649362035" alt=""><figcaption></figcaption></figure>
6. The approver may change the start and end date, if required; refer to the dynamic form attributes passed during the application assignment.
7. To continue the flow click on Accept button.
8.  Now the next level of approver will be able to see the previous levels of approval, and similar to the previous level of approval, the approver may change the start and end date, if required; refer to the dynamic form attributes passed during the application assignment.\


    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003452839/original/szqPQHWWV4Dr4usjPr9vApQUe8eOcRHGYQ.png?1649362063" alt=""><figcaption></figcaption></figure>
9. Click “Accept” to proceed.
10. After the last level approver has also approved the assignment, the backend processes will run the application provisioning flow.
11. Once the user has been provisioned in the application, they will be able to see it in their list of applications.

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003452855/original/yIiCVFhX-xmZBLAib632fRt2FOo2gfsddg.png?1649362113)

### 4. Bulk Assignment of application to a set of users

An administrator can bulk assign an application to a set of users. This an be achieved by uploading a .csv file which contains user information like.,  loginId, appUserId and  roleId.\
\
For bulk assigning applications to users in Cymmetri platform administrator needs to

1. Click on **Identity Hub > Applications** menu and then click on the **Applications Assignments** button.

<figure><img src="../../../.gitbook/assets/image (138).png" alt=""><figcaption></figcaption></figure>

2. A screen pops up that lets you select the csv file you want to upload that contains the list of users to whom the application needs to be assigned, Upload the csv file, you may also use the sample data file available and modify it to match your user details.

<figure><img src="../../../.gitbook/assets/image (139).png" alt=""><figcaption></figcaption></figure>

3. Click on the **Upload File** button and select the file you wish to import

<figure><img src="../../../.gitbook/assets/image (140).png" alt=""><figcaption></figcaption></figure>

4. Once the file is selected ensure that the default parameters select match your requirement else you may change these parameters as per your requirement.
5. Once you have ensured the parameters are correct next select the application that needs to be assigned and click on **Next** button.

<figure><img src="../../../.gitbook/assets/image (141).png" alt=""><figcaption></figcaption></figure>

6. Match the Column names from the CSV file with the corresponding attributes using this File Info dialog box and click on the **Import** button.

<figure><img src="../../../.gitbook/assets/image (142).png" alt=""><figcaption></figcaption></figure>

_**Note:** The "Link Application" check box is available to provision the user in the target application_&#x20;

7. Once Imported results of successfully Imported Users, Duplicate Users or any error that occurred during import can be see in **Logs > Import History** page

<figure><img src="../../../.gitbook/assets/image (143).png" alt=""><figcaption></figcaption></figure>

8. If any workflow is configured on the application provisioning then the corresponding workflow is triggered after the successful completeion of assignment as shown below:

<figure><img src="../../../.gitbook/assets/image (621).png" alt=""><figcaption></figcaption></figure>
