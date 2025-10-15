# Provisioning

In any Identity and Access Management (IAM) system, provisioning rules are predefined instructions or policies that dictate how user accounts and access privileges are automatically created, modified, or deactivated across various IT systems and applications.&#x20;

These rules streamline the process of managing user identities and access rights throughout their lifecycle within an organization.

In Cymmetri, administrators have the ability to establish these rules within the "Rules" tab under the Lifecycle Management module. To do so, the administrator navigates to the "Provision" section, where the following page will be displayed.

<figure><img src="../../../.gitbook/assets/image (564).png" alt=""><figcaption></figcaption></figure>

On this page, administrators can view a comprehensive list of all the currently established rules within Cymmetri, along with an "Edit" button that allows them to make modifications to these rules.

On the top right corner of the page the admin can find the **Add New** button to add a new provisioning rule in Cymmetri.&#x20;

<figure><img src="../../../.gitbook/assets/image (632).png" alt=""><figcaption></figcaption></figure>

To add a new rule you must do the following:

* Add the name of the rule&#x20;
* Add Description of the rule&#x20;
* Activate the rule&#x20;

<figure><img src="../../../.gitbook/assets/image (633).png" alt=""><figcaption></figcaption></figure>

Next select one or more applications with their corresponding roles (if defined).&#x20;

<figure><img src="../../../.gitbook/assets/image (623).png" alt=""><figcaption></figcaption></figure>

If necessary, roles can be created for the application directly within the provisioning rule before adding them.

<figure><img src="../../../.gitbook/assets/image (624).png" alt=""><figcaption></figcaption></figure>

Note: Multiple application and roles can be added in a single provisioning rule&#x20;

<figure><img src="../../../.gitbook/assets/image (625).png" alt=""><figcaption></figcaption></figure>

Just the way multiple applications can be assigned to users during provisioning, administrator can also assign one or more groups during the provisioning process.

For assigning groups the administrator needs to go to the Groups Tab and click on **+Add New Group** button.

<figure><img src="../../../.gitbook/assets/image (626).png" alt=""><figcaption></figcaption></figure>

Next a drop down appears where the user may select the group that the user needs to be a part of. Administrator may also assign multiple groups if required.

<figure><img src="../../../.gitbook/assets/image (627).png" alt=""><figcaption></figcaption></figure>

The next step is to add the condition upon which the rule will be activated within the system.

### Filtering Conditions

To add a condition navigate to the conditions section and click on **+ Add Condition** button.&#x20;

<figure><img src="../../../.gitbook/assets/image (628).png" alt=""><figcaption></figcaption></figure>

You can set up multiple conditions for the rule. For example, in the rule below, the conditions are that the user must be an "Employee," and their department should be "Sales."

A group of conditions can be added to be true/ false together.

The AND/ OR Switch allows to toggle if all the conditions are associated with an AND condition or an OR Condition

If required these conditions can be added, deleted or modified.

<figure><img src="../../../.gitbook/assets/image (629).png" alt=""><figcaption></figcaption></figure>

Once all the configurations are done the page needs to be saved. The Provision Rule creation page after all the configurations appears as below:

<figure><img src="../../../.gitbook/assets/image (631).png" alt=""><figcaption></figcaption></figure>

These rules automate and streamline the process of managing user accounts and access privileges across various systems and applications within an organization.
