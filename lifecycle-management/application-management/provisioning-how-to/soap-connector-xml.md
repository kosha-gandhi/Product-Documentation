# SOAP Connector (XML)

Inside User Configuration, add the Base Addresses of the target system SOAP APIs and add the  Create, Update, and Delete Groovy Scripts. These scripts will perform the related CRUD operations at the target system using SOAP.

<figure><img src="../../../.gitbook/assets/image (936).png" alt=""><figcaption></figcaption></figure>

It is an example where the Create Script will be added. Similarly, add the other Scripts under the User Configuration

<figure><img src="../../../.gitbook/assets/image (941).png" alt=""><figcaption></figcaption></figure>

Add Relevant Connector Server, Port, and other details under the server configuration tab.

<figure><img src="../../../.gitbook/assets/image (953).png" alt=""><figcaption></figcaption></figure>

a.        Set up Policy Attributes.

&#x20; Go to the Policy Attributes on the left side menu. Add the user attributes that need to be involved in the CRUD Operations as named in the target system.

<figure><img src="../../../.gitbook/assets/image (954).png" alt=""><figcaption></figcaption></figure>

b.      Set up Policy Map

This corresponds to the mapping of the fields in the target system with Cymmetri Fields

<figure><img src="../../../.gitbook/assets/image (955).png" alt=""><figcaption></figcaption></figure>

&#x20;Step 1: Add and configure a new Custom Web Services Application

a.       Go to Applications > Add New > Change Application Label > Click on Add Application.

<figure><img src="../../../.gitbook/assets/image (956).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (957).png" alt=""><figcaption></figcaption></figure>

This will add the application to be provisioned.

b.      Set up Application Provisioning

&#x20;   Once the application is added, open the application and click on the provisioning

To add a mapping, click on the add Cymmetri field and add the field details.

Application Field - Field name of the target application

Cymmetri Field- Field name in the Cymmetri.

Check Is USER Principal option for the uniqueness of that particular field as per the target system,

Check Create Only and Update Only if the CREATE/UPDATE    operation is required for that field.

Click on Save.

<figure><img src="../../../.gitbook/assets/image (958).png" alt=""><figcaption></figcaption></figure>

Now the application is ready for provisioning.

Step 2:  Add/Update/Delete Application to the User.

Go to the user to whom the application needs to be assigned. Click on the add new button. Now select the newly created application for provisioning and click on assign.

<figure><img src="../../../.gitbook/assets/image (959).png" alt=""><figcaption></figcaption></figure>

Configure the Application Access Details and click on Save

<figure><img src="../../../.gitbook/assets/image (960).png" alt=""><figcaption></figcaption></figure>

Now User is Assigned to the target application.

Along with the Cymmetri adding the target application and its details to its database, the target application too will save the user details of the cymmetri.

&#x20;Sending the details to the target application is done using a rest connector whose configuration is done under the provisioning section in step 1. This rest connector has groovy scripts for CRUD Operations.

The create groovy script is used to create the user in the target application.  This create script prepares the required payload by referring to the policy attributes and policy mapping and calls the target system’s CREATE API. The target application returns a UID which is used for future purposes like update and delete. &#x20;

<figure><img src="../../../.gitbook/assets/image (961).png" alt=""><figcaption></figcaption></figure>

We can edit the user details from the user profile. Along with updating the details into Cymmetri this will call the Update Groovy Script present in the User Configuration and perform the update operation in the target application for the user.

<figure><img src="../../../.gitbook/assets/image (962).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (963).png" alt=""><figcaption></figcaption></figure>

Delete a User is deprovisioning the user from the application. This is done using the delete option. This calls the delete groovy script to remove the user from the target application thus deprovisioning it. Once deleted the user is removed from the target system.

<figure><img src="../../../.gitbook/assets/image (964).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (965).png" alt=""><figcaption></figcaption></figure>

Step 3: Reconciliation/Syncing(PULL) user data into Cymmetri from the Target System.

The synchronization code is written inside the sync Groovy script. Sync Script fetches the user data from the target system and passes it to the Cymmetri, which further processes it according to the reconciliation condition specified.

<figure><img src="../../../.gitbook/assets/image (966).png" alt=""><figcaption></figcaption></figure>

Reconciliation is started by creating a reconciliation object under the tab mentioned below.

<figure><img src="../../../.gitbook/assets/image (967).png" alt=""><figcaption></figcaption></figure>

Click on ADD New to create a new Reconciliation PULL object. Add the cymmetri(Sync Field) and Target field (Source Attributes) mapping against which the sync action will be performed.

<figure><img src="../../../.gitbook/assets/image (968).png" alt=""><figcaption></figcaption></figure>

Now specify the pull conditions as per the requirement and click on save. A new recon object is created.

<figure><img src="../../../.gitbook/assets/image (969).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (970).png" alt=""><figcaption></figcaption></figure>

Click on the edit option on the recon object to run the reconciliation.

Clicking on Run Now will trigger the reconciliation PULL Process.

<figure><img src="../../../.gitbook/assets/image (971).png" alt=""><figcaption></figcaption></figure>

Reconciliation history can be checked under the history tab.

<figure><img src="../../../.gitbook/assets/image (972).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (974).png" alt=""><figcaption></figcaption></figure>

### Assumptions and Observations

·         The Target Application considered is any SOAP API and the groovy scripts are created to call these soap APIS.

·         CRUD and Sync Groovy Scripts added in this Word document remain the same except for a few changes.

a.       The request body of the target system to be sent will change. It will be in the form of a String XML.

b.       The Sending/Receiving Response of the SOAP web services will remain the same.

c.       Once the XML response is received from the SOAP API, this response has to be parsed into JSON by reading the child nodes of the XML.

d.       After a user is created into the target system using the create groovy script, the user ID received in the xml response has to be parsed and saved. This UID is used later for update/delete operations.

e.       Sync records received from target soap API has to be parsed and collected into an array and passed to the Cymmetri.
