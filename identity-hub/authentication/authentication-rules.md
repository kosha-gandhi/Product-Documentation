# Authentication Rules

Within Cymmetri, the authentication process is highly customizable through the definition of authentication rules. While the platform provides a default authentication rule, administrators have the ability to define custom authentication rules that align with the specific business needs and the variety of identity providers at their disposal.

For instance, let's consider a scenario where an organization has distinct user types, such as regular employees, contractors, and administrators. The administrators might require to authenticate employees with Active Directory as the identity provider and use Cymmetri's own authentication engine to verify the identity of vendors and contractors. With Cymmetri's flexibility, administrators can create authentication rules that cater to these varying requirements, ensuring a tailored and secure authentication experience based on user roles and organizational needs.

<figure><img src="../../.gitbook/assets/image (220).png" alt=""><figcaption></figcaption></figure>

Admins can find authentication rules in Authentication tab in Cymmetri.&#x20;

To create a new authentication rule, admin must simply click on the "Add New" button on the top right corner of the page.&#x20;

<figure><img src="../../.gitbook/assets/image (501).png" alt=""><figcaption></figcaption></figure>

The admin must fill in the following details

1. The name of the rule&#x20;
2. Identity provider radio button ( Enable for External IDP  or Disable for Internal IDP)
3. Identity provider&#x20;
4. Description of the rule&#x20;
5. Active Radio Button

**Conditions**&#x20;

The administrator has the capability to establish rules based on conditions like: Department, designation, User Type, country, and Login Pattern.&#x20;

Subsequently, the administrator defines regular expressions for conditions, specifying whether they should be equal to, not equal to, and assigns corresponding values.&#x20;

Cymmetri facilitates the creation of multiple conditions for an authentication rule and provides the option to group these conditions using AND or OR logic.

<figure><img src="../../.gitbook/assets/image (495).png" alt=""><figcaption></figcaption></figure>

In the image presented above, an exemplar authentication rule is showcased. This rule is structured to authenticate a user in Cymmetri through Active Directory if two conditions are met: the user's department must be equal to "Compliance," and the user type should be "Employee."&#x20;

Similarly If you wish to set the Identity provider for users having email address ending with "@cymmetri.com" then you may select condition as LoginPattern > Regular Expression and its value as (.)\*(@cymmetri.com)+$; and save the details.

<figure><img src="../../.gitbook/assets/image (583).png" alt=""><figcaption></figcaption></figure>

This demonstrates how authentication rules can be precisely configured to suit specific criteria and streamline the authentication process based on defined conditions.
