# Application Level MFA

The administrators can configure Application-Level Multi-Factor Authentication (MFA) to require an additional layer of verification for specific applications. This is done through a Sign-On Policy within the Identity Hub → Application → Sign-On Policy menu.

The Sign-On Policy allows an admin to select an application and require users to perform an additional authentication step, even if they've already logged into Cymmetri's Identity Hub.

This granular control is highly beneficial because it allows organizations to enforce security policies where they're most needed without creating unnecessary friction for users accessing less sensitive applications. It provides a flexible and adaptive security model, ensuring that the highest levels of security are applied to the most critical data and systems. This selective approach balances security with user experience.

<figure><img src="../.gitbook/assets/image4 (2).png" alt=""><figcaption></figcaption></figure>

### Configuration Process

Administrators can set up application-level MFA by following a structured, step-by-step process.

Step 1: Policy Creation and Conditions

The administrator begins by creating a new policy by selecting "+Add New".

<figure><img src="../.gitbook/assets/image5 (2).png" alt=""><figcaption></figcaption></figure>

The policy's application is governed by a set of conditions that can be combined using either AND or OR logical operations. These conditions allow for granular control and can be based on various user attributes, including:

* User Type
* Designation
* Department
* Country

<figure><img src="../.gitbook/assets/image2 (2).png" alt=""><figcaption></figcaption></figure>

#### Step 2: Policy Exclusions

After defining the conditions, the administrator can create exceptions to the policy. This allows for specific users or groups to be excluded from the MFA requirement, providing flexibility for internal workflows or special cases where MFA is not necessary.

<figure><img src="../.gitbook/assets/image3 (2).png" alt=""><figcaption></figcaption></figure>

#### Step 3: Access

The administrator can select from a range of predefined options to determine the frequency with which users are prompted for a second authentication factor. These options offer a balance between security and user convenience:

* Every Time: Requires MFA on every single login attempt, providing the highest level of security for highly sensitive applications.
* Once per session: Prompts for MFA once per browser or application session. The user is not prompted again until the session ends.
* Once a day: Requires MFA once every 24 hours.
* Every 12 hours: Prompts for MFA every 12 hours from the last successful authentication.
* Once a week: Requires MFA once every seven days.
* Once a month: Prompts for MFA once every 30 days.
* Once every six months: Requires MFA once every 180 days.
* Only once: Prompts for MFA only during the initial login to the application. This is typically used for applications with a very low-risk profile.

<figure><img src="../.gitbook/assets/image1 (3).png" alt=""><figcaption></figcaption></figure>
