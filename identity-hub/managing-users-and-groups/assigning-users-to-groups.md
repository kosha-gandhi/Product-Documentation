# Assigning Users to Groups

## Assigning Users to a Group

Users once created in the Cymmetri platform can be assigned to a group. Assigning users to a group helps ease the administrative efforts to apply the same policies and assign applications to multiple users.

When assigning users to groups, various approaches can be used:

* Adding User to Group (from the Group Page)
* Assigning a Group to a User (from the User's Page)
* Bulk Assigning Users to a Group (Using Group Assignment on Group Page)

### Adding User to Group <a href="#assigninguserstoagroup-addingusertogroup" id="assigninguserstoagroup-addingusertogroup"></a>

First, the administrator needs to click on the group name and enter the configuration for the group.

<figure><img src="../../.gitbook/assets/image (824).png" alt=""><figcaption></figcaption></figure>

Now, go to the Users Page and click on the **+Add** button to get a list of users to add to the group

<figure><img src="../../.gitbook/assets/image (825).png" alt=""><figcaption></figcaption></figure>

3\. Now, click on the assign button next to the user you wish to add to the group. Once assigned, the user can be seen on the Users page of the Group as shown below:

<figure><img src="../../.gitbook/assets/image (269).png" alt=""><figcaption></figcaption></figure>

### Assigning a Group to a User

For this approach, the Administrator needs to go to **Identity Hub > User** page and then select the user from the list to whom the group needs to be assigned

<figure><img src="../../.gitbook/assets/image (270).png" alt=""><figcaption></figcaption></figure>

Go to the user's page, select the **Groups** menu, and click on the "**+Assign New**" button

<figure><img src="../../.gitbook/assets/image (271).png" alt=""><figcaption></figcaption></figure>

This opens a pop-up window where a list of all groups is visible

<figure><img src="../../.gitbook/assets/image (272).png" alt=""><figcaption></figcaption></figure>

Click on the assign button, and the group is assigned to the user, or you may say the user becomes a part of the group

<figure><img src="../../.gitbook/assets/image (273).png" alt=""><figcaption></figcaption></figure>

### Bulk Assigning Users to a Group

For this approach, the Administrator needs to go to **Identity Hub > Group** page and then click on the **Group Assignment** button

<figure><img src="../../.gitbook/assets/image (274).png" alt=""><figcaption></figcaption></figure>

A screen pops up that lets you select the CSV file you want to upload to import the users that need to be assigned to the group. This CSV file needs to have one column that contains the login ID of users. Upload the CSV file, you may also use the sample data file available and modify it to match your user's login ID.

<figure><img src="../../.gitbook/assets/image (275).png" alt=""><figcaption></figcaption></figure>

Once the file is selected and uploaded, next you need to select the group to which you want to assign the users.

<figure><img src="../../.gitbook/assets/image (264).png" alt=""><figcaption></figcaption></figure>

After selecting the group, the column in the CSV file needs to be mapped with the Cymmetri login column.

<figure><img src="../../.gitbook/assets/image (265).png" alt=""><figcaption></figcaption></figure>

Once mapped, click on the import button, and the users will be mapped to the assigned group, provided the login ID is correct

<figure><img src="../../.gitbook/assets/image (267).png" alt=""><figcaption></figcaption></figure>

Results of successfully Imported Users, Duplicate Users, or any errors that occurred during import can be seen in the **Logs > Import History** page

<figure><img src="../../.gitbook/assets/image (266).png" alt=""><figcaption></figcaption></figure>
