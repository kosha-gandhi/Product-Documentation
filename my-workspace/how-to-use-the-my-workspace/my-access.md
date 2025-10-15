# My Access

Cymmetri provides an interface where users can view the applications assigned to them from where they can access such applications using Single Sign-On (SSO). The SSO ensures that users do not need to remember the username and password to access the desired application. Users can also request access to applications not yet assigned or entitled to them by providing the necessary information.

<figure><img src="../../.gitbook/assets/image (832).png" alt=""><figcaption></figcaption></figure>

### Application

The Application section under My Access provides user easy and friction-less access to the applications they want to use.&#x20;

Applications can be assigned to the user using the Cymmetri Provisioning framework, either as a birth-right (default) access, or through Provisioning Rules as defined by the Administrator.&#x20;

For applications requiring approval, the Cymmetri Workflow processes such access requests before granting access to the user.

<figure><img src="../../.gitbook/assets/image (322).png" alt=""><figcaption><p>Application Section</p></figcaption></figure>

### Requesting an Application



{% hint style="info" %}
**Note**: Cymmetri provides the ability to set up On Demand Access. Below is the default Request for Access feature.&#x20;
{% endhint %}

User can view the available applications after click on the Request button on the Application page under My Access. &#x20;

<figure><img src="../../.gitbook/assets/image (834).png" alt=""><figcaption></figcaption></figure>

The user can view all the applications that are available for the organization. The applications already assigned to the user are indicated by a green check mark.&#x20;

<figure><img src="../../.gitbook/assets/image (833).png" alt=""><figcaption></figcaption></figure>

&#x20;The user can request for any application not already assigned to them by clicking on the required application tile.  \
The user is required to select the period of access - either a Start and End Date for access or opt for Lifetime Access. After the selection, the user can submit the request by clicking the Save button.

&#x20;<img src="../../.gitbook/assets/image (336).png" alt="" data-size="original">&#x20;

Depending on the configuration performed by the Administrator, the user will be assigned to the application or the approval request for the user’s access will be initiated. ![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003395694/original/NeCGXrGedHnUA4byCxgRqE7k-n4sdjX4Rg.png?1649312342) \
After all the approvals are granted, the user will be assigned to the application. ![](<../../.gitbook/assets/image (338).png>)

### Search an Application

The search bar on the Application page allows users to quickly search an application by its name. To use the search, click on the search icon followed by typing the name of the desired application. &#x20;

<figure><img src="../../.gitbook/assets/image (835).png" alt=""><figcaption></figcaption></figure>

The search result is automatically displayed for the matching applications below :&#x20;

<figure><img src="../../.gitbook/assets/image (836).png" alt=""><figcaption></figcaption></figure>

The search for applications is across the tags defined by the user. &#x20;

### Performing SSO&#x20;

The user can access any application by simply clicking on the desired application tile. Cymmetri will initiate the authentication request to the target application, and here, the user will get authenticated to the desired application in a new browser tab or window.  &#x20;

<figure><img src="../../.gitbook/assets/image (837).png" alt=""><figcaption></figcaption></figure>

User accessing the applications which are assigned on time bound basis, will show a snippet defining the access period. This is for the user’s information. The snippet is visible while user hovers over the application tile. &#x20;

![](<../../.gitbook/assets/image (323).png>)&#x20;

### Managing Application Options&#x20;

As a user self-service action, applications assigned to the user can provide the user with options to manage their access. Clicking on the menu button under an application tile opens a context menu for that application.&#x20;

![](<../../.gitbook/assets/image (324).png>)&#x20;

#### Assign Role

The Assign Role context menu, allow users to change or request for change the role assigned to them.  If there is no approval required for the requested role, the system will automatically assign the role to the user.&#x20;

![](<../../.gitbook/assets/image (325).png>)&#x20;

#### Remove Role

The remove role context menu, allow users to remove the role assigned to them. If there is no approval required for the requested role, the system will automatically assign the role to the user.&#x20;

![](<../../.gitbook/assets/image (326).png>)&#x20;

#### Request Extension&#x20;

Cymmetri allows user to extend their access period for applications with time-bound access.  ![](<../../.gitbook/assets/image (329).png>)

The user can opt the Request Extension option from the application context menu. &#x20;

![](<../../.gitbook/assets/image (328).png>)\
Cymmetri shows the current access end date. The user is required to select a new access end date and click on Request button.

&#x20; ![](<../../.gitbook/assets/image (330).png>)

\
On successful submission, the user can view the success message. If a workflow is configured on the application access then a workflow gets triggered and the extension is granted only after the approval of the workflow.&#x20;

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003395667/original/xS2MIRR6OPPmOoB4LTBXl-sZeU46blaMsQ.png?1649312341)&#x20;

### Tags

Tags allow for easy categorization of applications as desired by the user. When a user is assigned numerous applications tags help in categorizing them and allowing easy management of applications.

#### Create a Tag &#x20;

To add a tag, click on Create New Tag button. Provide the desired name and click on Create button.&#x20;

<figure><img src="../../.gitbook/assets/image (838).png" alt=""><figcaption></figcaption></figure>

Once submitted successfully, the tag is visible on Application page. &#x20;

<figure><img src="../../.gitbook/assets/image (839).png" alt=""><figcaption></figcaption></figure>

#### Move to Tag&#x20;

User can move applications from the All Applications section to any tag as desired. Click on the menu button inside an application tile, select the option Move to Tag. &#x20;

![](<../../.gitbook/assets/image (331).png>)&#x20;

Once the tag is clicked, the system will move the application to the respective tag and user will see the sucess message. &#x20;

<figure><img src="../../.gitbook/assets/image (840).png" alt=""><figcaption></figcaption></figure>

\
User can now view the application under the tag by clicking on the tag name. &#x20;

![](<../../.gitbook/assets/image (332).png>)&#x20;

User can move an application from one tag to another tag by following the above mentioned process.&#x20;

#### Managing Tags &#x20;

The user is allowed to create Tags to manage the applications assigned into different sections for ease of access.  User can create up to 4 tags. After user creates the fourth tag, the Create New Tag button is disabled. &#x20;

![](<../../.gitbook/assets/image (333).png>)

A user cannot create a tag with an existing tag name. Cymmetri will show an error "_Tag with same name already exists_". &#x20;

![](<../../.gitbook/assets/image (334).png>)

#### Editing a Tag Name&#x20;

User can rename a tag anytime by clicking on the menu button on the tag and selecting Rename option. &#x20;

<figure><img src="../../.gitbook/assets/image (842).png" alt=""><figcaption></figcaption></figure>

Type in the revised name for tag and click Update button. &#x20;

<figure><img src="../../.gitbook/assets/image (841).png" alt="" width="425"><figcaption></figcaption></figure>

On successful update, the tag name is changed and user can see the success message. &#x20;

<figure><img src="../../.gitbook/assets/image (843).png" alt=""><figcaption></figcaption></figure>

#### Deleting a Tag&#x20;

User can opt to delete a tag using the the delete tag option on clicking the Delete option.&#x20;

<figure><img src="../../.gitbook/assets/image (844).png" alt="" width="563"><figcaption></figcaption></figure>

Clicking on Delete will show a warning and once approved the tag will be removed.

![](<../../.gitbook/assets/image (335).png>)

&#x20;On successful delete, the tag is removed and user can see the success message. &#x20;

<figure><img src="../../.gitbook/assets/image (845).png" alt=""><figcaption></figcaption></figure>

Deleting the tag will not remove the applications assigned to user. The applications can always be viewed under All Applications. &#x20;
