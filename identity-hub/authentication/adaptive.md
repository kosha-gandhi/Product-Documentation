# Adaptive

Adaptive authentication is an advanced security measure that assesses various factors and context elements in real-time to determine the level of risk associated with a user's access attempt.&#x20;

Based on this risk assessment, the authentication system can dynamically adapt its level of scrutiny and request additional verification steps if needed. This approach enhances security while minimizing disruption for legitimate users.

In Cymmetri there are various adaptive checks that the admin can enable for additional factor of authentication.



<figure><img src="../../.gitbook/assets/image (243).png" alt=""><figcaption></figcaption></figure>

1. **Device Trust Check** - If enabled, Cymmetri will check if the device being used to perform action on the Cymmetri portal, has been trusted by the user
2. **User Behavior** - Cymmetri determines whether the behavior of user matches with the known behavior pattern of the user over time
3. **Blacklisted IP** - Maintains a blacklist of IP addresses that are known to be sources of unauthorized access, hacking attempts, or other malicious activities
4. **Blacklisted Location -** Cymmetri maintains a list of locations from which the administrator wishes to restrict access of the portal
5. **Short Lived Domain -** Cymmetri checks the email address domain of the user with a database of known providers of short-term or disposable email addresses
6. **Impossible travel scenario -** Tracks the change in location of user attempting an action over a short period of time and flagging if, system deems the pattern to be impossible.

The admin can enable these checks as per the business use case

To navigate to the adaptive settings page, click on the "Go to settings" button on the top right corner of the page.&#x20;

### **IP Address Checks**

Administrators can include an IP address in the blacklist by following these steps:

Enable the "IP address Check" radio button at the top of the page, input the IP address into the "Blacklisted IP address" field, and press enter. The specified IP will be added to the list. To synchronize the list with the database, click the "Sync Now" button.

<figure><img src="../../.gitbook/assets/image (588).png" alt=""><figcaption></figcaption></figure>

You can select additional actions when module detects an anomaly. They are the following:

* **Ask additional MFA and notify** - If an MFA rule has been established and adaptive authentication is activated for it in the MFA section, when a user attempts to log in with a blacklisted IP address, the user will be prompted for additional factor(s) for authentication as defined by the rule. Additionally, the user will receive email notifications regarding the login activity.

<figure><img src="../../.gitbook/assets/image (589).png" alt=""><figcaption><p>Push Notification as MFA for Blacklisted IP check on Login</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (590).png" alt=""><figcaption><p>Email on user's registered Email ID </p></figcaption></figure>

* **Only Notify** - This option solely sends a notification to the user about the login activity.
* **Block user and notify** - This option not only blocks the user upon a login attempt with a blacklisted IP but also notifies the user on their registered email ID.

### **Device Trust**

Define how Cymmetri determines if a device is trusted for the user and allows to define behavior of authentication in Cymmetri, in case of untrusted device

The admin can define

1. No of successful authentication attempts
2. Number of devices per user&#x20;
3. Number of days&#x20;
4. Additional action when module detects anomaly

<figure><img src="../../.gitbook/assets/image (242).png" alt=""><figcaption></figcaption></figure>



* **Location based checks**

Organizations can maintain a list of blacklisted locations as part of their adaptive authentication strategy to enhance security measures and mitigate potential risks

The admin can select the blacklisted location on this page. Also additional actions on these checks can be selected.

<figure><img src="../../.gitbook/assets/image (240).png" alt=""><figcaption></figcaption></figure>

* **Impossible Travel Scenario**

Track the changes of location from which the user attempts to perform actions on the portal over a short period of time and flags an action attempt

The admin can configure the:

1. Check Windows(in hrs)
2. Average Distance (in Km)

<figure><img src="../../.gitbook/assets/image (237).png" alt=""><figcaption></figcaption></figure>

* **Short lived Domain Checks**

Checks the .email address domain of the user with a database of known providers of short-time or disposable email addresses

The admin can Sync the database where the domains are stored and updated

<figure><img src="../../.gitbook/assets/image (238).png" alt=""><figcaption></figcaption></figure>

* **User behavior checks**

Cymmetri determines whether the behavior of user matches with the known behavior pattern of the user over time

The admin can select the required checks to verify the consumer behavior:

1. Unusual time of Login
2. Unusual number of Login failures
3. Unusual keystrokes pattern

<figure><img src="../../.gitbook/assets/image (239).png" alt=""><figcaption></figcaption></figure>

The admin can enable, configure and save these adaptive checks individually as and when required.
