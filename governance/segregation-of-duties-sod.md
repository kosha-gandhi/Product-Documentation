# Segregation Of Duties (SOD)

Cymmetri provides a framework for managing risk arising for application access to organization users. Broadly, the risk is quantified on the basis of Qualitative and Quantitative measures

**Qualitative Risk**

This is a risk that is identified from the knowledge of the system. This means that even in absence of the Enterprise Role model or mapping of activities or tasks or processes to the users, a certain risk value may still be assigned to the users, purely based on the application roles based on the COSO framework (i.e. admin / maker / checker / read only) and applications assigned to them.

The qualitative risk calculation will be based on -

* The number of applications assigned to a particular user, the risk associated with the application, and
* The risk associated with the COSO type of the application role.

**Quantitative Risk**

This is a risk that is identified from the specific classification of application roles based on High, Medium and Low risk. The risk classification is thus based on users having roles assigned to them.

### SOD Features

As a part of Cymmetri’s Identity Governance & Administration capabilities, Segregation of Duty (SoD) is offered as a product feature.

Also called Separation of Duty, the SoD in principle is the demarcation of access grant with respect to business functions pertaining to a job / task.

The current functions by the SoD in the product provide-

Ability to configure the following under Entities:

1. Business Tasks
2. Business Roles
3. Business Process

Ability to configure the following under Policies:

1. SoD Policies
2. SoD Rules

To establish the activities performed by the organisation, the Cymmetri Admin will configure the Business Process. Under each Process, there will be one or several tasks to accomplish the business activities. For example, a task could be “Transaction Entry up to 50,000” or “Transaction Approval above 1,00,000” or “Manage Masters”

For each of the tasks, there will be Business Roles such as “Approve Transactions” or “Book Transactions” or “Manage System Configuration”

Example in tabular form:

<table data-header-hidden data-full-width="true"><thead><tr><th width="284"></th><th width="306"></th><th></th></tr></thead><tbody><tr><td><strong>Business Process</strong></td><td><strong>Business Role</strong></td><td><strong>Business Task</strong></td></tr><tr><td>Purchase</td><td>Book Purchase Transactions</td><td>Transaction Entry up to 50,000</td></tr><tr><td>Transaction Entry between 50,001 - 99,999</td><td></td><td></td></tr><tr><td>Transaction Entry above 1,00,000</td><td></td><td></td></tr><tr><td>Purchase Approval</td><td>Approve Purchases Transactions</td><td>Approve up to 50,000</td></tr><tr><td>Approve between 50,001 - 99,999</td><td></td><td></td></tr><tr><td>Approve above 1,00,000</td><td></td><td></td></tr><tr><td>Maintain System</td><td>Configure System</td><td>Add &#x26; Modify Master records</td></tr><tr><td>Delete or Disable Master records</td><td></td><td></td></tr><tr><td>Manage Users</td><td>Add &#x26; Update Users</td><td></td></tr><tr><td>Delete or Disable Users</td><td></td><td></td></tr><tr><td>Assign or Remove Role to Users</td><td></td><td></td></tr></tbody></table>

Based on the above entity information, we can define Policies for defining the separation of duties

| **SoD Policy**                 | **SoD Rule (roles that cannot co-exist)** |
| ------------------------------ | ----------------------------------------- |
| Maker cannot be checker        | Book Purchase Transactions                |
| Approve Purchases Transactions |                                           |
| Admin cannot have other roles  | Configure System                          |
| Book Purchase Transactions     |                                           |
| Admin cannot have other roles  | Configure System                          |
| Approve Purchases Transactions |                                           |

**Linkage of Business Role with Application Role**

When the SoD Admin is configuring the Business Role, they must link the record to an Application Role configured in Cymmetri. Thus the SoD Business Role and Application (IT) Role are interlinked providing Cymmetri with the mechanism for mapping business role to application role.

![](<../.gitbook/assets/1 (1).png>)

Apart from the above configurable elements, it is important to note that Applications configured in Cymmetri also allow defining the application risk categorization along with role type categorization. These elements together provide Cymmetri to define a Qualitative and Quantitative Risk score to every user based on the applications assigned and the role entitlement available with the user.

The benefit this provides in Cymmetri is that when a requester has asked for a role which may have potential conflicts, the approver is made aware of the same. Along with the conflicting roles (toxic combinations), it also allows approver to see the risk score associated with providing approval.

![](<../.gitbook/assets/2 (1).png>)

Violation example

![](<../.gitbook/assets/3 (1).png>)

### Configuration aspects

#### Defining Business Tasks

![](<../.gitbook/assets/4 (1).png>)

![](<../.gitbook/assets/5 (1).png>)

#### Defining Business Roles

![](<../.gitbook/assets/6 (1).png>)

#### Linking Business Tasks with Business Roles

![](<../.gitbook/assets/7 (1).png>)

#### Linking Business Tasks with IT (Application) Roles

![](<../.gitbook/assets/8 (1).png>)

#### Defining SOD Access Policy

![](<../.gitbook/assets/9 (1).png>)

#### Define SOD Access Rule

![](<../.gitbook/assets/10 (1).png>)

#### Associate SOD Access Policy with SOD Access Rule

![](<../.gitbook/assets/11 (1).png>)

#### Defining SOD violations or toxic combinations:

* Setup Business Roles
* Setup Business Tasks
* Associate Business Role with Application Role
* Setup SoD Policy
* Setup SoD Access Rule
  1. Define Violations

![](<../.gitbook/assets/12 (1).png>)
