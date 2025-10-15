# Importing Users

Users may be imported into the Cymmetri platform using the bulk Import Users feature.

_<mark style="color:green;">Please Note: User import process follows the synchronization policies as defined</mark>_ [_<mark style="color:green;">here</mark>_](../../lifecycle-management/application-management/reconciliation-how-to/configuring-reconciliation-process.md#synchronizing-scenarios-and-their-corresponding-outcomes)_<mark style="color:green;">.</mark>_

### Importing Users

For Importing Users in the Cymmetri platform administrator needs to click on **Identity Hub > User** menu and then click on the **Bulk Import > Import Users** button.

<figure><img src="../../.gitbook/assets/image (276).png" alt=""><figcaption></figcaption></figure>

A screen pops up that lets you select the CSV file you want to upload to import the users, Upload the CSV file, you may also use the sample data file available and modify it to match your user details.

<figure><img src="../../.gitbook/assets/image (277).png" alt="" width="380"><figcaption></figcaption></figure>

Click on the **Upload File** button and select the file you wish to import

<figure><img src="../../.gitbook/assets/image (278).png" alt=""><figcaption></figcaption></figure>

Once the file is selected ensure that the default parameters selected match your requirements else you may change these parameters as per your requirement and click on the **Next** button.

<figure><img src="../../.gitbook/assets/image (279).png" alt=""><figcaption></figcaption></figure>

Match the Column names from the CSV file with the Cymmetri User Attributes using this File Info dialog box.

<figure><img src="../../.gitbook/assets/image (280).png" alt=""><figcaption></figcaption></figure>

Scroll down and click on the **Import** button.\
\
&#xNAN;_**Note:** A "Skip user workflow" check box is available to skip execution of any user workflow configured for the creation of users, if not selected it may trigger user creation workflow, and the process of importing users may slow down due to the numerous approvals that the approver might have to do._

Once Imported results of successfully Imported Users, Duplicate Users, or any error that occurred during import can be seen in **Logs > Import History** page

<figure><img src="../../.gitbook/assets/image (281).png" alt=""><figcaption></figcaption></figure>
