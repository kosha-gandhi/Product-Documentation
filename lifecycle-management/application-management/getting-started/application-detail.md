# Application Detail

The Application Detail Page provides comprehensive management features for applications within the system. It includes various sub-pages for configuring assignments, sign-on protocols, policies, provisioning settings, roles, and more. Below we outline the functionalities and configurations available on each sub-page.

<figure><img src="../../../.gitbook/assets/image (852).png" alt=""><figcaption></figcaption></figure>

### **Assignments**

This page allows administrators to assign users and groups to an application. Users or group members can access the application if it is configured for Single Sign-On (SSO) or get provisioned in the application if it is a provisioning application.

*   **Features**:

    * Assign users and groups to the application.
    * View and manage existing assignments.

    <figure><img src="../../../.gitbook/assets/image (853).png" alt=""><figcaption></figcaption></figure>

### **SignOn**

Configures the application for sign-on using various protocols.

<figure><img src="../../../.gitbook/assets/image (854).png" alt=""><figcaption></figcaption></figure>

* **Supported Protocols**:
  * **SAML**: Configure SAML-based single sign-on.
  * **OpenID**: Set up OpenID Connect for authentication.
  * **Reverse Proxy**: Configure reverse proxy settings for sign-on.
  * **API SSO**: Set up API-based single sign-on.
* **Features**:
  * Protocol selection and configuration.
  * Test and validate sign-on settings.
  * Manage sign-on settings for different environments.

### **SignOn Policy**

Configure Multi-Factor Authentication (MFA) for the application’s SSO settings.

*   **Features**:

    * Configure MFA prompts and policies.
    * Manage MFA settings to ensure secure access.

    <figure><img src="../../../.gitbook/assets/image (855).png" alt=""><figcaption></figcaption></figure>

### **Provisioning**

Configure application provisioning with various settings organized into tabs.

* **Tabs**:
  * **User Configuration**: Define application attributes and settings for provisioning.
  * **Server Configuration**: Set up connector server parameters.
  * **Operations**: View provisioning operations supported
  * **Hook Configurations**: Configure hooks for triggering provisioning actions.
*   **Features**:

    * Manage and configure provisioning details.
    * View and edit provisioning settings.
    * Monitor provisioning operations.

    <figure><img src="../../../.gitbook/assets/image (856).png" alt=""><figcaption></figcaption></figure>

### **Roles**

&#x20;Create and manage application roles and import roles from CSV files.

*   **Features**:

    * Create new roles.
    * Import roles via CSV for bulk role creation.
    * Manage and edit existing roles.
    * Ensure roles are correctly provisioned in target applications.

    <figure><img src="../../../.gitbook/assets/image (857).png" alt=""><figcaption></figcaption></figure>

### **Policy Map**

Configure mapping between the provisioning source application and Cymmetri user fields.

*   **Features**:

    * Define and manage field mappings for data synchronization.
    * View data mappings for User Pull Reconciliation.
    * Ensure accurate data exchange between systems.

    <figure><img src="../../../.gitbook/assets/image (858).png" alt=""><figcaption></figcaption></figure>

### **Settings**

Configure general settings for the application. This section allows you to modify application label and description. You may also configure other settings as shown below:

<figure><img src="../../../.gitbook/assets/image (859).png" alt=""><figcaption></figcaption></figure>

#### **Application Risk Level:**&#x20;

This section lets you set application's risk which enables for identifying overall risks for users. The Risk level can be set to **High, Medium, Low** and **Unknown**

<figure><img src="../../../.gitbook/assets/image (860).png" alt=""><figcaption></figcaption></figure>

#### **Visibility settings:**

Administrator may configure visibility settings as shown below

* **Show to User:** This setting when enabled lets the user see an application assigned to them.
* **User can request:** This setting when enabled lets the user to request an application which is not assigned to the user.

<figure><img src="../../../.gitbook/assets/image (861).png" alt=""><figcaption></figcaption></figure>

#### **Role settings:**&#x20;

Administrator may configure various role settings as shown below:

* **Multiple role assignments:** which allows a user to have multiple roles in the said application and&#x20;
* **Mandatory roles:** This setting mandates that when the application is assigned atleast one role is assigned to the user
* Add notes for end users and administrators.

### **Policy Attribute**

This page lets you configure all the attributes from the provisioning source whose data needs to be synced on either sides.

<figure><img src="../../../.gitbook/assets/image (862).png" alt="" width="563"><figcaption></figcaption></figure>

### **Reconciliation**

Configure reconciliation settings for data synchronization.

*   **Features**:

    * Set up pull reconciliations to retrieve data from the source application.
    * Configure push reconciliations to update data in the source application.
    * Manage reconciliation schedules and tasks.

    <figure><img src="../../../.gitbook/assets/image (863).png" alt=""><figcaption></figcaption></figure>

### **Forms**

Configure dynamic forms used in workflows for additional data collection.

*   **Features**:

    * Create and manage dynamic forms.
    * Configure forms to collect data during workflow processes.
    * View and edit form data as required by administrators and users&#x20;

    <figure><img src="../../../.gitbook/assets/image (864).png" alt=""><figcaption></figcaption></figure>

### **Tags & Meta**

Manage tags and meta information for applications.

*   **Features**:

    * Create and assign tags for categorization and search.
    * Add and manage meta information for various purposes.
    * Use tags and meta data to enhance application organization, search and categorization

    <figure><img src="../../../.gitbook/assets/image (865).png" alt=""><figcaption></figcaption></figure>

### **360 Degree Recon**

* **Description**: Provides a comprehensive reconciliation view for data synchronization across the system.
*   **Features**:

    * View detailed reconciliation data and statuses.
    * Analyze and resolve reconciliation issues.

    <figure><img src="../../../.gitbook/assets/image (866).png" alt=""><figcaption></figcaption></figure>
