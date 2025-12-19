# Masters in Cymmetri

Masters are key-value pairs that can be defined for the entire tenant. The key(name) in this context refers to the label to be shown on the Cymmetri User Interface, and the value is the backend identifier used to reference this field in various processes, rules, and policies defined in the Cymmetri platform.

<figure><img src="../../.gitbook/assets/image (1022).png" alt=""><figcaption></figcaption></figure>

Cymmetri platform allows for configuring several masters in the system, the major classification among which are Global masters (which allow for creating master key-value pairs that may be used for various situations, such as creating a new department, designation, and other custom attributes for users in the system) and Zone masters (which are network configurations that may be used to whitelist or blacklist user access onto the platform as well as act as a source for adaptive Multi-factor authentication).

### Global Masters

These are system-wide key-value pairs primarily used to setup key-value pairs referring to various masters as given below:

#### Types of Global Masters:

<table data-full-width="true"><thead><tr><th width="146">Type</th><th>Description</th></tr></thead><tbody><tr><td><strong>Country</strong></td><td>Country key-value pairs are stored in the system, and are available as drop-downs wherever needed in the system - User attributes, Policies and other mappings.</td></tr><tr><td><strong>UserType</strong></td><td>UserType is used as one of the conditions while defining authentication policies and as an input in the rule engine.</td></tr><tr><td><strong>Department</strong></td><td>Department is used as one of the conditions while defining authentication policies and as an input in the rule engine, and also as a user attribute.</td></tr><tr><td><strong>Designation</strong></td><td>Designation is used as one of the conditions while defining authentication policies and as an input in the rule engine, and also as a user attribute.</td></tr><tr><td><strong>RBAC</strong></td><td>RBAC (System Roles) is used as one of the conditions while defining authentication policies and as an input in the rule engine, and also as a user attribute.</td></tr></tbody></table>

### Adding a new Master

Follow the steps below to Add a New Master:

Click on the "**+Add New**" button to add a new master of any category mentioned above.

<figure><img src="../../.gitbook/assets/image (399).png" alt=""><figcaption></figcaption></figure>

Enter the Name and Value for the new Master, then select the type of master you wish to create and enable the active toggle button to make the master active. Once all values are entered, click on the **Save** button

<figure><img src="../../.gitbook/assets/image (400).png" alt=""><figcaption></figcaption></figure>

A new Global Master is successfully created in the selected category

<figure><img src="../../.gitbook/assets/image (402).png" alt=""><figcaption></figcaption></figure>

### RBAC Master

The RBAC Master allows the maintenance of role entitlements for the organization.

<figure><img src="../../.gitbook/assets/image (88).png" alt=""><figcaption></figcaption></figure>

### Zone Masters

Zone masters indicate the network zones that may be used for blacklisting or whitelisting access to the Cymmetri Identity platform deployment. It may also be used for detecting users from certain zones and assigning relevant multi-factor authentication policies.

<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003445189/original/mgekYllA80lOO9TAamYZDUuvgGIXO-glEQ.png?1649351539" alt=""><figcaption></figcaption></figure>

**Zone Name:** Used to refer to a zone in other configurations on the Cymmetri platform.

**Inactive/Active:** Toggle button to check whether the zone is active (configurable as a condition for other rules on the Cymmetri platform).

**Gateway IP:** Refers to the Gateway IP address for the network zone.

**Proxy IPs:** Proxy Server IP addresses that may be used to direct to this network or the IP addresses outside of the zone that would indicate a connection from this zone.

**CIDR:** Refers to the CIDR notation of the subnet of the network that this zone refers to. [CIDR Notation](https://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing).

For adding a new Zone Master or for editing an existing one, fill in all the mandatory details on the screen as shown above, click on the enable toggle button, and finally click the “Save” button.

A sample is shown below :

<div align="left"><figure><img src="../../.gitbook/assets/image (1023).png" alt="" width="389"><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (1024).png" alt="" width="392"><figcaption></figcaption></figure></div>

_Note: This screenshot shows sample/test data only and must not be used in production_

### Grade Master

The **Grade Master**  is a **Global Master** used to define numeric grades that categorize employees and establish hierarchical precedence. Grades are critical for building approval matrices in workflow rules that depend on organizational levels. Here we define **Grade Values** (numbers) and associated **Labels** (descriptions).

### Why numeric grades?

* Numeric grades allow clear **precedence ordering**.
* Lower numbers usually represent higher precedence (e.g., Grade 1 = Director).
* Easy comparison (e.g., Grade 2 > Grade 3) makes it suitable for workflows.
* Avoids ambiguity that text-only labels would create.

### Attributes

| Field           | Description                                                                        | Required |
| --------------- | ---------------------------------------------------------------------------------- | -------- |
| **Grade Value** | Numeric value representing the grade. Determines precedence logic. Must be unique. | Yes      |
| **Label**       | A descriptive label for the grade (e.g., “Manager”, “Executive”).                  | Yes      |
| **Status**      | Active / Inactive toggle. Only active grades can be used in workflows.             | Yes      |

### Configuration

#### Access

Go to **Admin → Configurations → Masters → Grade**.

#### View Grades

The Grade Master page displays a list of existing grades with:

* **Precedence** (from Grade Value)
* **Grade Value**
* **Label**
* **Status**
* **Actions** (Edit option)

<figure><img src="../../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

#### Add a Grade

1. Click **+ Add New**.
2. Enter **Grade Value** (numeric).
3. Enter **Label**.
4. Set **Status** (Active/Inactive).
5.  Click **Save**.<br>

    <figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

#### Edit a Grade

1. Click the **Edit** icon.
2. Update **Grade Label**, or **Status**.
3. Save changes.

<figure><img src="../../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

### Best Practices

* Keep Grade Values **numeric and unique**.
* Align numbers with your organizational hierarchy (e.g., 1 = most senior).
* Use meaningful **labels** for clarity.
* Set obsolete grades to **Inactive** rather than deleting them.
