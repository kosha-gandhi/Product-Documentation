# Roles Mining

Role mining is a systematic and analytical process designed to identify and extract existing access assignment patterns within an organization's current infrastructure. This involves comprehensively examining "who has access to what" to discern recurring groupings of permissions and entitlements. The overarching objective of this discovery phase is to define meaningful business roles, which represent logical job functions or responsibilities, rather than mere technical access groupings.

Cymmetri's methodology centers on the comparative analysis of these existing access assignments, leveraging specific, predefined attribute fields. These fields serve as critical dimensions for grouping users and identifying logical access patterns. Key examples include:

* **Department**: Categorizes users by their organizational unit.
* **Designation**: Groups users based on their job title or professional level
* **User Type**: Differentiates users by their employment status or category
* **Other Contextual Fields**: Additional relevant organizational or user attributes that facilitate the delineation of distinct access requirements.

Once these analytical fields are selected, Cymmetri generates "candidate roles." Each candidate role represents a potential business role derived from a specific, observed combination of these attributes chosen fields.

**Configuration and Execution of Role Mining in Cymmetri**

The role mining process in Cymmetri is structured into clear, sequential steps within the **Identity Governance module.**

**To initiate a new role mining project**: Navigate to the Identity Governance section and click on "**+ Add New**".

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXeHebWIQIoGNCoP6wQTKaBEp47NB9ZyKydlSGrhW5qaf1QTxc834LRa6jHCBMpQmG_81X25jbxTeNpPiRjVw81X2kQWdd5I6AIz0NQofTEp66NqURObxzv46h23rJ68X0GzN8aa?key=e82LlnAF5zKCn5Yi2h0HbQ" alt=""><figcaption></figcaption></figure>

\
**Step 1: Define Role Mining Details**

Provide essential identifying information for the role mining initiative:

* **Role Mining Name**: A unique and concise title that identifies the specific role mining project.
* **Role Mining Description**: Comprehensive descriptive information outlining the scope, objectives, and any relevant context for the role mining effort.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXfUFuCfFJ0dqeWWlCF6f6QT_LtrKtuBwt3Yi-L9dmrN47s7wOvrl5aSDLjGV4XjCjQ6Q24jsWl15Jgv_qRZ5qQJXPDE6qj9A6IAYaz3yB2TPPCaStaT6jnHJehX05myvQN4RdMXDg?key=e82LlnAF5zKCn5Yi2h0HbQ" alt=""><figcaption></figcaption></figure>

**Step 2: Select Role Mining Criteria**

Determine the basis for the role mining analysis by selecting the relevant user attributes:

* **Options Provided**:
  * Department
  * Designation
  * User Type
* **Administrator Control:** The administrator can flexibly select all available options for a more granular analysis or choose only the required ones to focus on specific dimensions.
* **Proceed**: After selecting the desired attributes, click "**Next**" to advance.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdLzp4DW3mKy8v3R6bEUcnvBJokjW3ZfT64z-3DzRJh1UACiFYYLwSivY2y3z_hm8QZb0pusJjk714Bu7ioX2H04M4qOreKVmP4GCW6hZpwaOWyG7UYZMENi1LSHXbeP5bFKbVhdA?key=e82LlnAF5zKCn5Yi2h0HbQ" alt=""><figcaption></figcaption></figure>

**Step 3: Generate Candidate Roles**

Based on the attributes selected in Step 2, the system will process the access data to "**Generate Candidate Roles**." This action initiates the analytical engine to identify and propose potential business roles.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXcmRDY3f-Fp4cZB0EUgrMAS0ldMbS19KSsCAJXnlXXr8UxtUU-t_1D26UMWTx72vGK2kp8YrE3miuBRo0M9uUSUjJtI3Rf965UkwGepTpRWEFR8y6MBA4qDbeuEwkO19tdqxTo6rw?key=e82LlnAF5zKCn5Yi2h0HbQ" alt=""><figcaption></figcaption></figure>

**Refining Candidate Roles: The Minimum Support Parameter Score**

The "**Filter Options**" feature provides administrators with a crucial mechanism to refine and control the granularity of the presented role mining results. This functionality is driven by the **minimum support parameter score**.

The **support parameter score**, expressed as a percentage, is a key metric calculated during the role mining process. It quantifies the statistical significance and consistency of a discovered access pattern, indicating the proportion of users within a particular grouping who consistently possess a specific set of application roles or permissions.

**Functionality of the Minimum Support Parameter Score**:

* **Setting the Threshold**: The administrator sets a minimum threshold for this support parameter. Only candidate roles and their associated application access patterns that meet or exceed this defined minimum score will be displayed as valid suggestions.
* **Higher Percentage for Accuracy and Precision**:
  * Setting a higher minimum percentage (e.g., 90% or 95%) ensures the system presents only highly consistent and prevalent access patterns. This yields more accurate and precise role suggestions, ideal for defining clear, widely applicable business roles with minimal exceptions.
* **Lower Percentage for Broader Discovery and Granularity**:
  * Conversely, a lower minimum support score (e.g., 60% or 70%) results in a broader display of candidate roles, including less universally consistent but still significant groupings. This offers wider discovery and allows for the identification of more granular or niche roles, presenting more potential fields and combinations for administrative review.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXeiitwfK7F-zewWGkd-k0JXh2zPPXQHrY9aX3hl7M3O7QiERBgEuD3Nry1kCLKlhKg_dXolTAUYJp2vyrgw-TQJKFq77YVdU9cIA-aI9y-6Uc5dLfY6yKGzzOZTXwW-gNptFX18Gw?key=e82LlnAF5zKCn5Yi2h0HbQ" alt=""><figcaption></figcaption></figure>

**Step 4: Review and Formalize Candidate Roles**

Upon completion of the role mining analysis and the application of any filters, the system presents the administrator with the **generated candidate roles** for review. The administrator can:

* **Systematically Review**: Examine each proposed rule.
* **Inspect Attributes**: Verify the underlying attributes that defined the rule.
* **Verify Conditions**: Review the specific logical conditions associated with the rule.
* **Assess Support Score**: Evaluate the calculated support score for each candidate.
* **Review Rule Name**: Observe the initial system-generated rule name.

For future access management and automation, a generated and validated candidate rule can be formalized into an active **provisioning rule**. This is achieved by:

* "**Generate Rule**" Action: Clicking this button transforms the candidate rule into an active provisioning rule within the system.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXcVRgjOL6bAK0hh4jDARQ0Hxq4luriIQQpu7vN0X0faBB0QWzDLQRPgddIN41fYrVpBVohSmUeDGz33-o-OP1wwPn5uB5SDhcbxrGPbqjL7M5bgDr4HKzAybvog3QbNoMn2llO-Ig?key=e82LlnAF5zKCn5Yi2h0HbQ" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXezZvXgVWDqwU1frUjQvLxuI-Ll8b_KqyGhbpuunxsgYQ-4ukkd58QAAfRa50GTDTzQKR1nXqBGUSXbJLek64_KJr_leFUjtOs8XMO9Pii6Ao9Q3OjOvTi414hA7VUwnDrGJhJuqQ?key=e82LlnAF5zKCn5Yi2h0HbQ" alt=""><figcaption></figcaption></figure>

**Verification Path**: The newly created provisioning rule can be verified under: Lifecycle Management -> Rules -> Provision

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXd17LgbqXT9W8OUqMCXWzLnam8eFBMSXho2IfKCAIO3qkkvkWX7oDxGrzWc5fpmGt2W-obeaf010GMFB52GaWY98Nk-wXuWpY-OMWNyL32gJL_S4JMT9fEgoxvx8TsGpqc4N2J8?key=e82LlnAF5zKCn5Yi2h0HbQ" alt=""><figcaption></figcaption></figure>

After a rule has been established as a provisioning rule, the system provides an interface for further refinement and detailed verification. The administrator retains the ability to edit key aspects of the provisioning rule, ensuring its ongoing accuracy and relevance:

* **Edit Rule Name**: Modify the formal name of the provisioning rule.
* **Edit Description**: Update the descriptive information for comprehensive context.
* **Verify Conditions**: Confirm the logical conditions that trigger the rule.
* **Verify Assigned Applications**: Review the specific application roles or permissions automatically assigned upon condition satisfaction.
* **Save**: All modifications must be explicitly saved to apply changes.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXcMZsEG96YocybDPXT5VuFlBcYh2CfF__rLfmDCkZCSYPjNZGkp_LLy4Z6uTxUBLV0r4nvkdeCxlSXC2WBZtyGM0zGR3i2RjGjBTRKzBzIhFfFc-dbEgjiU9OfCfWAVYyYjFryodQ?key=e82LlnAF5zKCn5Yi2h0HbQ" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXeXUVeAGxTkhRijbj5kn05fKx-8gHFQgbn9AE3ePMqSHv_B_0yf7F5sFZUksusGr3T7q3JX7vO3PfL5sYYMwSpd1B5vLXc0Kye4kZcapyfCcVmDSGRHs-pr01eWEVZ_XtPR61k3Og?key=e82LlnAF5zKCn5Yi2h0HbQ" alt=""><figcaption></figcaption></figure>

\
