# Recommendation Engine

The Cymmetri Recommendation Engine is a component of Cymmetri, designed to provide personalized recommendations based on user data and behavior. It leverages advanced statistical algorithms to analyze patterns and trends, and to provide personalized application and role recommendations to each user based on their attributes and historical data.

## Features

**Personalised User Experience:** Provides users with personalised suggestions for applications and roles based on their specific attributes, historical usage patterns, and peer behaviour.

**Operational Efficiency:** Reduces the manual workload of administrators by automating the process of assigning applications and roles.

**Security and Compliance:** Ensures that recommendations adhere to compliance policies by incorporating SoD checks, which prevent conflicting roles or application assignments.

The recommendation engine will employs a combination of collaborative filtering, content-based filtering, and a hybrid approach to ensure accurate and personalised recommendations.&#x20;

The system periodically fetches user data, processes it, and stores the recommendation scores and details in the database

In Cymmetri the recommendation engine calculates the recommendation scores and shows the recommendations as shown below:

<figure><img src="../.gitbook/assets/image (884).png" alt=""><figcaption></figcaption></figure>

The recommendation engine shows whether the access to the application should continue or be rejected. The approver may use the recommendation and perform the necessary action.

<figure><img src="../.gitbook/assets/image (885).png" alt=""><figcaption></figcaption></figure>

The administrator has choice of reviewing one or more application simultaneously and approve. If the user selects multiple reject requests to review it may appear as shown:

<figure><img src="../.gitbook/assets/image (886).png" alt=""><figcaption></figcaption></figure>

If multiple accept requests are selected they appear as shown below:

<figure><img src="../.gitbook/assets/image (887).png" alt=""><figcaption></figcaption></figure>

If user tries to approve multiple accept and reject requests and confirm the change the screen may appear as below:

<figure><img src="../.gitbook/assets/image (888).png" alt=""><figcaption></figcaption></figure>
