# On Demand Access

Cymmetri offers the capability  restrict users to requesting only specific roles or access rights. Administrators should be able to define on-demand roles that dynamically grant access based on criteria such as:

* Function Group
* Function
* Department
* Job

Users can request these roles, with each role having a dedicated approval matrix. Upon user request, the approval process will be initiated according to the configured workflow.

Additionally, any changes to a user’s attributes should automatically adjust their access if they already hold roles or permissions associated with an application, ensuring that access remains consistent with their updated profile.

## Cymmetri - Self Service Designer

Cymmetri provides the option to activate on-demand access. In cases where the administrator does not enable this feature, it will operate according to default [Request for Access](../my-workspace/how-to-use-the-my-workspace/) feature.

### Enable On-Demand Access

Condition-based-

<figure><img src="../.gitbook/assets/image (978).png" alt=""><figcaption></figcaption></figure>

### Request On-Demand Access

The administrator can choose either the application itself or the application with associated roles. Depending on the conditions, the user self-service page will display either the application or the application with roles.

<figure><img src="../.gitbook/assets/image (979).png" alt=""><figcaption></figcaption></figure>

### Exceptional Request&#x20;

The activation or deactivation of exception approval can be done within Cymmetri once the administrator enables this feature. The system facilitates the specification of exception-based requests through the self-service portal.

&#x20;Administrators will set conditions in the backend concerning:

* Function Group
* Function
* Department
* Job

The admin will map the applications along with roles.

Users will then choose the above criteria, and based on their function, they can select applications and associated roles.

When a user requests an exception for an application, only their associated functional group will initially appear, and they cannot switch to another functional group.

For instance, if the user's functional group is "Weighbridge," the function, department, and job will be associated accordingly.

Approval for exceptions will be initiated as required.



## User request process

**For On-Demand Access**

1.  User to select “On Demand” Request&#x20;

    <figure><img src="../.gitbook/assets/image (981).png" alt=""><figcaption></figcaption></figure>
2.  The user will be able to see the list of applications that he is eligible to request as per the logic defined&#x20;

    <figure><img src="../.gitbook/assets/image (982).png" alt=""><figcaption></figcaption></figure>
3.  The user will select the application that he wants access to and a pop-up will appear to select the role&#x20;

    <figure><img src="../.gitbook/assets/image (983).png" alt=""><figcaption></figcaption></figure>
4.  The user may select Lifetime/Time-Based access and then select the role from the drop-down.

    The drop-down will contain a list of on-demand roles as per the logic.

    Lifetime access:   &#x20;

    <figure><img src="../.gitbook/assets/image (985).png" alt=""><figcaption></figcaption></figure>

    Time based access:&#x20;

    <figure><img src="../.gitbook/assets/image (986).png" alt=""><figcaption></figcaption></figure>
5. The user shall save the request. And the approval workflow will be triggered as defined

**For Exceptional Access Request**&#x20;

1.  User to select “Exceptional Access” from the drop-down&#x20;

    <figure><img src="../.gitbook/assets/image (987).png" alt=""><figcaption></figcaption></figure>
2.  The user will see the filters of HR attributes and based on the filters selected will get the list of applications&#x20;

    <figure><img src="../.gitbook/assets/image (988).png" alt=""><figcaption></figcaption></figure>
3.  The user will select the application that he wants access to and a pop-up will appear to select the role. The drop-down will contain a list of on-demand roles as per the logic.

    Lifetime access:&#x20;

    <figure><img src="../.gitbook/assets/image (989).png" alt=""><figcaption></figcaption></figure>

    Time-based access:&#x20;

    <figure><img src="../.gitbook/assets/image (990).png" alt=""><figcaption></figcaption></figure>
4. The user shall save the request. And the approval workflow will be triggered as defined.



