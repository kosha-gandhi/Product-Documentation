# CSV Directory (Flat-file)

Cymmetri provides a connector to remotely connect to a data source using SFTP and fetch flat-files to manage application user assignment data in Cymmetri. database provisioning involves setting up and managing database access for provisioning users from the Database Management System into Cymmetri. The CSV Directory can import common data types such as Comma Separated Values, Delimited Files or Flat-files from a configured location.&#x20;

## Configuration

To configure the CSV Directory with Cymmetri we need to configure the CSV Directory application. Please follow the steps provided below.

First we need to create one CSV file locally then we need to place this file in the server.

For example if we connected to the server 10.0.0.99 then we need to place the csv file on that server. For example, we can transfer the file through the WinSCP application as well.

Click on the CSV Directory application from Cymmetri application catalogue

<figure><img src="../../../.gitbook/assets/image (924).png" alt=""><figcaption></figcaption></figure>

1. After Getting application from Cymmetri master activate provisioning of selected application i.e. CSV Directory.
2. After successfully activating provisioning, setup server configuration.

**Note**: Basic configuration is already provided in Cymmetri master application. If the connector server is configured externally then configure server config as per requirement.

&#x20;

<figure><img src="../../../.gitbook/assets/image (923).png" alt=""><figcaption></figcaption></figure>

3. Successfully configuring server configuration, next step is to configure User Configuration. This is the most important step to connect and perform operations with CSV Directory.

There are some fields which are compulsory

**Source Path**: Absolute path of a directory where the CSV files to be processed are    located.

**File Mask**: Regular expression describing files to be processed. It can be the name of the csv file name.

**Key Column Names**: Name of the column used to identify user uniquely

**Ignore header**: Specify it first line file must be ignored

**Column names**: Column names separated by comma

Here the column name is the same as csv files column name.

**Field Delimiter**: Delimiter used to separate fields in CSV files

**Key separator**: Character used to separate keys in a multi-key scenario

<figure><img src="../../../.gitbook/assets/image (925).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (926).png" alt=""><figcaption></figcaption></figure>

Now fill the above fields and save the configuration and test the configuration.

Now we have to add Policy Attribute as per requirements. Go to Policy Attribute and click on Add New button.

<figure><img src="../../../.gitbook/assets/image (927).png" alt=""><figcaption></figcaption></figure>

After clicking on the new button we have to add Policy Attribute.

Now we also need to map the Policy Attribute name and description and save it.

After completing Policy Attribute we need to map these attributes with the Cymmetri fields.

Go to Policy Map and for user Policy Map click on Add Cymmetri Field.

<figure><img src="../../../.gitbook/assets/image (928).png" alt=""><figcaption></figcaption></figure>

&#x20;After clicking Add Cymmetri Field, window will open

<figure><img src="../../../.gitbook/assets/image (929).png" alt=""><figcaption></figcaption></figure>

Add the relevant field and map it to the appropriate Cymmetri Field and save. Similarly, add all the required fields and this completes the mapping activity before setting up the [reconciliation ](../reconciliation-how-to/)task.
