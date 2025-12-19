# Database Provisioning

In Cymmetri, database provisioning involves setting up and managing database access for provisioning users from the Database Management System into Cymmetri.

## Configuration

To configure a Database application for provisioning we need a database on the server. We need one table in the database on which we want to create  users.&#x20;

<figure><img src="../../../.gitbook/assets/image (732).png" alt=""><figcaption></figcaption></figure>

In the above image Userdetails is a table with some basic fields.

### Configuring the Database Application

To configure Database Application with cymmetri we need to configure ScriptOn (Database) Application. Please follow the steps provided below.

1.  Get ScriptOn (Database) Application from Cymmetri Master apps list

    <figure><img src="../../../.gitbook/assets/image (733).png" alt=""><figcaption></figcaption></figure>
2.  After Getting application from Cymmetri Master activate provisioning of selected application i.e ScriptOn application (Database).After successfully activation of provisioning, setup server configuration.

    <figure><img src="../../../.gitbook/assets/image (734).png" alt=""><figcaption></figcaption></figure>

_Note: Basic configuration is already provided in cymmetri master application. If the connid server is configured externally then configure server config as per requirement._

4. After successfully configuring server configuration, next step is to configure User Configuration. This is the most important step to connect and perform operations with ScriptOn (Database) applications.
5. To configure User configuration please refer to the following steps (It is abstract level steps that may be vary as per client). Following are the basic configuration which is required for every ScriptOn (Database) application to connect.
   1.  Database :- Name of the database on the database server that contains the table.

       <figure><img src="../../../.gitbook/assets/image (736).png" alt=""><figcaption></figcaption></figure>
   2. Datasource Path :- JDBC Data Source to connect to the database server.
   3.  Host :- The name of the host where the database is running.(eg localhost or 10.0.1.7)

       <figure><img src="../../../.gitbook/assets/image (739).png" alt=""><figcaption></figcaption></figure>
   4.  JDBC Driver :- The JDBC Driver class name.&#x20;

       Eg:  For Oracle Driver Class Name is oracle.jdbc.driver.OracleDriver\
       &#x20;       For MySQL is org.gjt.mm.mysql.Driver\
       &#x20;      For PostgreSQL is org.postgresql.Driver<br>

       <figure><img src="../../../.gitbook/assets/image (740).png" alt=""><figcaption></figcaption></figure>
   5. JDBC Connection URL :- Specify the JDBC Driver Connection URL. \
      Examples:\
      Oracle: jdbc:oracle:thin:@\[host]:\[port(1521)]:\[DB]     \
      MySQL: jdbc:mysql://\[host]:\[port(3306)]/\[db]\
      PostgreSQL template is jdbc:postgresql://\[host]:\[port(5432)]/\[db]
   6.  Db is a database name.  It Could be empty if a datasource is provided.

       <figure><img src="../../../.gitbook/assets/image (741).png" alt=""><figcaption></figcaption></figure>
   7. User Password :- User account that has permission to access accounts table.
   8. Port :- The port number the database server is listening on. For postgreSQL it could be 5432. For mysql it could be 3306. We need to use it according to our database.
   9. Reload Script On Execution :- This flag value must be true if we pass scripts file name (Groovy Scripts upload in server)
   10. User :- The name of the mandatory Database user with permission to the account table.
   11. Test Script or Test Script File Name :- Test script for testing connection from database with Cymmetri
   12. Create Script or Create Script File Name :- Create user script for creating user in database application (supports PostgreSQL, MySQL, Oracle 11g) \<uid needs to return from create script>
   13. Update Script or Update Script File Name :- Update user script for updating user in database application (supports PostgreSQL, MySQL, Oracle 11g) \<user update based on uid>
   14. Delete Script or Delete Script File Name :- Delete user script for deleting user from database application (supports PostgreSQL, MySQL, Oracle 11g) \<user delete based on uid>
   15. Search Script or Search Script File Name :- Search script for searching user from database (Bulk search)
   16. Sync Script or Sync Script File Name :- Sync script for Synchronizing users from database into/from cymmetri.

Above are the most important fields in user configuration which need to be configured. The details for the above fields are given in the application configuration page.

6. Configuring all the user and server configuration with proper data and Test application for connectivity. If it is successful then we can proceed for assignment and reconciliation operations or if it fails then check the audit log for error.
7. Other than user and server configuration we need Policy Attribute and Policy Map for mapping attributes of Database application with Cymmetri.&#x20;
8. Following are the steps to configure policy attribute and policy map.
   1. Policy Attribute :- There is default policy attribute cymmetri master application provides which has basic fields which needs to be configured for performing provisioning operation.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXeJ-aMMNbt1t1P8Zal2wyVNzSR8qz1qXRyNJ6p7a2sNYlR82cBYQWO6VMHVp_XcGY1GF6rg5IoSBdx-smtU-1aBrHAl3s-SmT6A3W7n2CWHEjZoyOHdON8rnj3IkPaHn46pArVEU-FwNArK07-DF9IK_M6T?key=i7amAoi6blGra30BJM0BCQ" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXfspX6L20CKrdcLetTnagtr1GiKyubrAXTO3oJeUVTGTTIcm2pVh1YRStK0p_5Fh6C4fK-1m1ziV9A-1I786JYSA-7MEmd-fF7UNIiRcOuTSik41A0IiDMTXDBc7aED4MFQTj5J0ecZ6FiHF1I7XZ2rpQsJ?key=i7amAoi6blGra30BJM0BCQ" alt=""><figcaption></figcaption></figure>

2.  To add a new policy attribute click on the new button and add policyAttribute and its description.

    <figure><img src="../../../.gitbook/assets/image (742).png" alt=""><figcaption></figcaption></figure>
3.  Policy Map :- There is default policy map present in cymmetri master application which provides basic mapping of ScriptOn (Database) application with cymmetri. To configure these mapping we need to activate it as in create only and update only flags need to be true as per requirement.

    <figure><img src="../../../.gitbook/assets/image (743).png" alt=""><figcaption></figcaption></figure>
4.  To add a new policy map click to Add Cymmetri field.

    <figure><img src="../../../.gitbook/assets/image (744).png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXeaxxP_aE5RnDfRIktZa-xX5M04rzq4pXc7GR5D4n2c_ueqIWgu0xj7W7_GaTiRJDw2KZ0Rz4BYuPm4FOkEqrNwyEBPcuq3e9l4AqRFb_fKxSTLOGLWA1k2FShgZYu9KM-YRzK-v3Thf8kZVI8LcbX2QOGY?key=i7amAoi6blGra30BJM0BCQ" alt=""><figcaption></figcaption></figure>

8. Some important policy map fields which need to be declared in the policy map are as follows.
   1. \_\_NAME\_\_ :- users login (supports from ‘cloud\_2.7.21’)
   2. \_\_PASSWORD\_\_ :- users password (supports from ‘cloud\_2.7.21’)
9. For sample script please validate following link

[https://drive.google.com/drive/folders/1-XSIlHSnf6UM0JYiaysA5Vg-TdfrMe0I?usp=drive\_link](https://drive.google.com/drive/folders/1-XSIlHSnf6UM0JYiaysA5Vg-TdfrMe0I?usp=drive_link)

10. We need to provide Groovy code to run create user, update user, delete user and also recon pull and push (for recon pull we need to add sync script and for recon push we need to add search script)

Note: Please Configure script step by step

1. Configure test script at initial step and then test configuration for provided script (If configure successfully then only go for step b).
2. Configure create script and test configuration (If successfully configured then only go for step c).
3. Configure update script and test configuration (If successfully configured then only go for step d).
4. Configure delete script and test configuration (If successfully configured then only go for step e).
5. Configure sync(pull) script and test configuration (If successfully configured then only go for step f).
6. Configure search(push) script and test configuration (If successfully configured then only go to the next step).

NOTE :- While configuring the database you need to add a jdbc jar for a particular database into connid server (Inside the lib folder of the connid server).
