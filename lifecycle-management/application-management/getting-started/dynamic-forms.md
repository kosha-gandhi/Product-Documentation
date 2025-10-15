# Dynamic Forms

Dynamic Forms enable administrators to request additional fields from either administrators or end-users when assigning applications. These additional user fields are then collected and used for provisioning the user into the managed application.

### Creating a dynamic form:

For creating a dynamic form the administrator needs to configure the managed application. For e.g. **Identity Hub->Applications->Service Now(Application may change )->Forms**

Load the default form by clicking on the “Load Sample Data” button

<figure><img src="../../../.gitbook/assets/image (146).png" alt=""><figcaption></figcaption></figure>

Edit the default form in the **JSON Schema** section, In the JSON Schema section the administrator can define the form structure with the type of element, and its various properties like type, title, default value etc., a preview of the form is shown on the right hand side.

Let us create a simple form that can capture&#x20;

1. “Preferred Username” \[text field] and&#x20;
2. “Request Additional Modules” \[Radio] with two options “Administrator” and “Read Only”.

The code below shows how to create a simple form described above:

<pre class="language-json" data-overflow="wrap"><code class="lang-json">{ 
<strong>  "type": "object", 
</strong>  "required": [ 
    "preferredName" 
  ], 
<strong>  "properties": { 
</strong>    "preferredName": { 
    "type": "string", 
    "title": "Preferred Username", 
    "default": "" 
  }, 
  "additionalModules": { 
    "type": "string", 
    "title": "Additional Modules", 
<strong>    "enum": [ 
</strong><strong>      "admin", 
</strong>      "readonly" 
    ], 
    "enumNames": [
       "Administrator",
       "Read-Only" 
    ], 
    "default": "" 
    } 
<strong>  }
</strong>}
</code></pre>

<figure><img src="../../../.gitbook/assets/image (620).png" alt=""><figcaption></figcaption></figure>

The **UI Schema** is like a set of json properties that are used to configure how the form should look and behave. It lets you tweak things like the length of a text box or whether a choice should be shown as radio buttons or checkboxes. In the example code, we're using the UI Schema to make the "preferredName" field have a placeholder and also set a maximum length. For "additionalModules," we're using widget property to make it show up as a radio button.

```
{
  "preferredName": {
    "placeholder": "Enter preferred name",
    "maxLength":5
  },
  "additionalModules": {
    "ui:widget": "radio"
  }
}
```

The **Preview Form Data** displays how the data entered in the UI will be gathered and shows the structure in which the data will be sent to the API.

<figure><img src="../../../.gitbook/assets/image (578).png" alt=""><figcaption></figcaption></figure>

The preview of the form looks as below after making the changes:

<figure><img src="../../../.gitbook/assets/image (579).png" alt="" width="370"><figcaption></figcaption></figure>

Once configured the administrator can Click on the Save button.

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003453247/original/rv1xlOomrNqjVWATvEPk4P9nDxtxUF8n9Q.png?1649362681)

Once saved a confirm box appears to enable the form; the administrator needs to click on the **Confirm** button in the popup to enable the form for the application.

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003453249/original/oLJcRIFKG72bSjV6y7MMxG-lMKAgsFwcWQ.png?1649362689)

### Form Options

There are four options in that can be configured after enabling forms in Cymmetri

![](<../../../.gitbook/assets/image (144).png>)



1. **Form View**: If enabled, the user has the option to see the application request form within the My Access section.
2. **Form Edit**: If enabled, the user has the option to edit the application request form within the My Access section, this will make changes in the respective fields in the target application.
3. **Role Assignment:** If activated, the user will be displayed the request form for applications that are already assigned to them when attempting to request additional roles.
4. **Role Unassignment:** If activated, the user will be displayed the form for applications when he/she is raising requests for role removal.

