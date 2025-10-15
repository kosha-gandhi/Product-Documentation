# Break Glass Configuration

**What is break glass configuration**?

"Break glass configuration" in Cymmetri refers to a method of obtaining the list of username and passwords of vault users without resetting them. It involves setting up special user accounts that can be used in emergencies to generate an envelope of vault user credentials and send it as a email to the configured user.

For configuring the user(s) we need to select the user(s) from the dropdown as shown below and need to enter a password.

<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84028181423/original/fD1_np28hlb9Nm-B50rAThpb7aQ3hyWVfw.png?1678272812" alt=""><figcaption></figcaption></figure>

\


![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84028181470/original/eQQ-Ar3fXhF7ummAe-KEBUB0zeyGh1Tc1g.png?1678272854)

Sending the vault user credentials can be done in two ways:

1.  Configure a scheduler which sends the email at the configured date-time and mentioned frequency as shown below:

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84028181510/original/uV4R2OzK-UPgPsG_BwrR_kTqqxFKjZx3cg.png?1678272876" alt=""><figcaption></figcaption></figure>
2.  Generate and send the envelope manually for All or specific user(s) as shown below:

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84028181567/original/N2J5V2DX5gq5srjWMU1BFgNyLzaPx8Dh0A.png?1678272896" alt=""><figcaption></figcaption></figure>

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84028181584/original/eRUWLtzmPw3qy5t0T2eGZB4Ef0DJUvoxsQ.png?1678272914" alt=""><figcaption></figcaption></figure>

&#x20;

\


The email sent to the configured user consists of a .csv file containing user details in encrypted format as shown here:

<div data-full-width="true"><figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84027754948/original/4sgrC1_zUk1WMzpWkEzih9jlTwgZHF2YTg.png?1677836873" alt=""><figcaption></figcaption></figure></div>

\


<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84027754984/original/6mM5ppiQv5q991o8Idn8lGhXnLYe_Rf-pQ.png?1677836901" alt=""><figcaption></figcaption></figure>

The User then needs to use a Utility called **PassEnvelopeReader** to decrpyt the encrypted data and view the list of usernames and password. This utility asks for a password at the beginning to be able to access and decrypt the user details.

<figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84027755389/original/iQ7zVwjMeP_EKrllYNRTSkwIwapNmes2Pg.png?1677837111" alt=""><figcaption></figcaption></figure>

\
