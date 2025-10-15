# Adding a device/ server in PAM

A **device or server** represents the critical systems within an organization.Servers play a critical role in Privileged Access Management (PAM) solutions, as they are often the targets of unauthorized access by attackers seeking to gain control over critical systems and sensitive data.&#x20;

&#x20;               PAM solutions manage and control privileged access to these systems. By leveraging PAM solutions to manage privileged access to servers, organizations can improve their security posture, reduce the risk of data breaches, and comply with regulatory requirements.&#x20;

&#x20;   In Cymmetri it is the Actual Server(Windows or Linux) that the Privileged User will be connecting to using either RDP or SSH.

Cymmetri allows you to add this device/ server.&#x20;

\


The steps to add a RDP device or server are as below:

1.  Click on the Devices sub-section on the PAM Page and click on the Add Server Button&#x20;

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84027974002/original/FMyyIB2NukDziL1brcRLwvMg1BCdDbdygA.png?1678102615" alt=""><figcaption></figcaption></figure>
2.  This opens up a new window for adding a server and it gives two options: **RDP(Remote Desktop Protocol)** and **SSH(Secure Shell Protocol)**., we need to select RDP for a _Windows Server_ and SSH for a _Linux Server_. Currently we will select RDP as we want to add a Windows Server

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84027974208/original/nhE4xdA-cAxwgLID9TmncI7AlrLBlt5z0w.png?1678102640" alt=""><figcaption></figcaption></figure>
3. When you select RDP a pop up shows up on the right and it asks for 3 details i.e.
   1. Device Label
   2. Hostname and
   3.  Username

       <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84027974518/original/kCRFTvgBVOXW9OKwXo_Cmcbnz5wg8vjgig.png?1678102712" alt=""><figcaption></figcaption></figure>
4. Device Label represents name of the device/ server and hence has to be unique.
5. HostName is the actual server name or its ip.
6. Username represents the actual server username to be used to connect to the server.
7. We will change these details as given below:
   1. Device Name: _Windows RDP Server_&#x20;
   2. Hostname: _65.0.122.207_&#x20;
   3. Username: _Administrator_\

8.  And then click on **Add Device** button to add the server

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84027974706/original/v_iFM9R5dym_tIzEjefLf-Mk5m0dsiBI0Q.png?1678102764" alt=""><figcaption></figcaption></figure>
9.  To check if the device is correctly added Click on Devices again and you can see the newly added server should be visible as shown below

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84027974776/original/riujBAVcUlSLY8V4WUbpA6bb1Db_agVuVg.png?1678102799" alt=""><figcaption></figcaption></figure>

\


The steps to add a SSH device or server are as below:

1.  Click on the Devices sub-section on the PAM Page and click on the Add Server Button

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84027974813/original/l2KTSw73eCglwA308qlPBHO2qTY3sjcGnQ.png?1678102823" alt=""><figcaption></figcaption></figure>
2.  Now from the two options available we need to select SSH

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84027974898/original/Nr58eZBh5D7ogwKIcFPPOCvelE7VADDioA.png?1678102870" alt=""><figcaption></figcaption></figure>
3.  A similar popup like in RDP opens up with Device Label prefilled.

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84027974961/original/cU1cj7uUxr4-p87_nCFtz4CFxtrT6b3-Zg.png?1678102897" alt=""><figcaption></figcaption></figure>
4. We need to change the Device Label, Hostname and Username as given below:
   1. Device Name: _Linux SSH_
   2. Hostname: _10.0.1.7_
   3.  Username: _kiran_

       <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84027975094/original/TTLUU1DMxR0uD7gCBAj3hREoCdXGCJHwEQ.png?1678102944" alt=""><figcaption></figcaption></figure>
5.  We then click on Add Device to add the Server and it can be seen in list as shown below:

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84027975172/original/_rd5rE988N_MsoXhb2xOVVi8Md_b-WdH9w.png?1678102975" alt=""><figcaption></figcaption></figure>

&#x20;

When a device is added it is added with minimum configuration, i.e. Device Label, Hostname and Username. You can further configure the connection and other device related information if it needs to be customized

For configuring the device further the steps are as follows:

1.  Click on the device you want to configure

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84027975301/original/JbWI5K3Khty72KiZN63tDKsBxtw7Oq9IAw.png?1678103008" alt=""><figcaption></figcaption></figure>
2.  Click on Settings

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84027975467/original/1dFz7GDlcTJvgeBxfBwUk4P2U-gY5QDgOw.png?1678103054" alt=""><figcaption></figcaption></figure>
3.  A Settings Page opens when you can find numerous options to configure as show below:

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84027975602/original/zv_ksPHPfpiXkJk3oFH6Q6eYnMbD2HNX4Q.png?1678103082" alt=""><figcaption></figcaption></figure>
4.  Connection Attributes for any device are read-only as show here, but other attributes can be configured

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84027637242/original/Ty4mBnd_D6j3TbMq7yVPbp3S9Q3Qu4vXEg.png?1677739859" alt=""><figcaption></figcaption></figure>
5.  Shown below are the attributes of a device/ server that can be configured:\


    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84027975733/original/MZHSJ_MVuI4-TZj4R6RXKr12-TqX1Rp_HQ.png?1678103117" alt=""><figcaption></figcaption></figure>

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84027976303/original/6osXkeVCReLMKlY_CrS1aHamoCX2RxqOJA.png?1678103228" alt=""><figcaption></figcaption></figure>

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84027976487/original/toDUugeyxkyzoUh02w7CLDmCwof4cf7zNg.png?1678103271" alt=""><figcaption></figcaption></figure>

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84027976582/original/rrx26ik-7-Vi_QvxqD5OF0kJiEsOkt2v-g.png?1678103295" alt=""><figcaption></figcaption></figure>
