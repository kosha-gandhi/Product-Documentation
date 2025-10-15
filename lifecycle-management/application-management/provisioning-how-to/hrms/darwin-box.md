# Darwin Box

Darwin Box Provisioning in Cymmetri involves integrating the Darwin Box HR management system with Cymmetri's identity and access management platform to automate and streamline user provisioning processes.

## Configuration

* Add the Darwin Box application from the master and Enable the application provisioning.
* Next we do User and Server Configurations

### &#x20;User Configuration:

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXf7NZXz2jQ7AzN1MXcHn5KoU44_l-F9yydNjHuEfpLbctr1Cm45fFcSs3KUk7GT1l6u3lS-iwMFmne-tfVbKixCoCtvb4F9tvnQQj0xGZJQIBU7aMDB6azWKcr4uNt23NowFhnTFACoU7FVMhDqrt-Tx0k?key=3d3esZorHsLho0dGQLM9_g" alt=""><figcaption></figcaption></figure>

1. Api Key: \<api\_key\_value>&#x20;
2. Username: \<username>
3. Password: \<password>
4. Dataset Key: \<dataset\_key\_value>
5. Unique key: employee\_id
6. Base Address: \<base\_address\_value>
7. Full Sync: \<Select accordingly if want to do full sync or partial sync>

### Server Configuration:

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXeLisF3C25E5NTJfcc2h-zQ4_sc1VzLqQUm85LCKuqnen3KfKS7B8vXOnJTF41Vev44AAUFxjHutSHV46g8-BYAeDimLsoP_htGsX3MHzdlgUH5ykoHhKMlNXxb49lCwGTqURna49QjZEV-XrfVDpz3d-Ls?key=3d3esZorHsLho0dGQLM9_g" alt=""><figcaption></figcaption></figure>

1. Host Server: 10.0.1.8
2. Server Password: \<password>
3. Server Port: 8760
4. Server Connector bundle name: darwinBoxRest
5. Server Connector bundle version: 1.0
6. Server Connector name: com.cymmetri.connector.darwinBoxRest.DarwinBoxRestConnector

### Add custom attributes (optional):

1. Group Company
2. Function
3. Office Area
4. Work Area Code
5. Office City
6. Direct manager employee id
7. Office mob no
8. Centre type
9. Office State
10. Office Address

### Add policy attributes in application

1. first\_name
2. last\_name
3. employee\_id
4. departments\_hierarchy
5. company\_email\_id
6. designation\_title
7. office\_country
8. group\_company
9. function
10. office\_area
11. work\_area\_code
12. office\_city
13. direct\_manager\_employee\_id
14. office\_mobile\_no
15. center\_type
16. office\_state
17. office\_address

### Map the policy attributes

1. employee\_id with login
2. first\_name with firstName
3. last\_name with lastName
4. company\_email\_id with email
5. employee\_id with employeeId
6. group\_company with Group Company
7. function with Function
8. departments\_hierarchy with department
9. office\_area with Office Area
10. work\_area\_code with Work Area Code
11. office\_city with Office City
12. office\_country with country
13. direct\_manager\_employee\_id with Direct manager employee id
14. office\_mobile\_no with Office mob no
15. center\_type with Center type
16. &#x20;office\_state with Office State
17. designation\_title with designation
18. office\_address with Office Address

### Create a reconciliation

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXesqvDrxIRlWVTvgAqdoHIR41lBT_62rSpJxPhxy-1evP25WupKTlZa4YbXOWPRyp3rBGbZC_7broEcgA79SEGrv8t7YtG4O2BxTRyMyaKliCF7f76pwERRGWBkboHzj4jBKieVPLOa6t9I_VFA_AEqvSM?key=3d3esZorHsLho0dGQLM9_g" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXc1AjKkxPajMigXiO8JAFUTTDQKaqTmMhiWQ8tsSKC8LhBFoy48-LXu01qW3rPga6HpPMG3nDtNgp9OS0EmszbXC3IAXRnQhCKNRja7K6qqZGnESfZLibHXeplFiYRFtFgmVbZBiGkLMVLYYP5YcvV-_y2V?key=3d3esZorHsLho0dGQLM9_g" alt=""><figcaption></figcaption></figure>

Create and  Run the reconciliation pull.

## Custom Script for date

Add the following script for date conversion in hook config

<figure><img src="../../../../.gitbook/assets/image (898).png" alt=""><figcaption></figcaption></figure>

## _Note:_

1. _For now, only sync operation is supported for Darwin Box._
2. _Unique key is considered as an employee id._
