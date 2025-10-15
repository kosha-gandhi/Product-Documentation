# Configuring Webhooks

Webhooks are a way for external systems to receive events from the Cymmetri Identity Platform.

Requires the tenant organization to run a web server that is exposed to the Internet or at least accessible from the Cymmetri Cloud 2.0 deployment on the cloud

Events may be received for the following events -&#x20;

1.  Testing Webhook - Generates a POST request to the /test endpoint of the web server hosted by the tenant. It provides an authorization token that can be used for making any API calls to the Cymmetri Cloud 2.0 APIs. Is generated after this configuration.\
    \
    Go to the Configuration Menu and Select the webhooks menu -\
    \


    Click on the save & test button.\
    \


    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003440699/original/aFQWevUqkU3Ac0_VaM8mTW7G_K3QE2GK1g.png?1649346917" alt=""><figcaption></figcaption></figure>
2. Pre Create User - Generates a POST request, before the user is created, to the /preCreateUser endpoint of the web server hosted by the tenant.
3. Pre Update User - Generates a POST request, before the user is updated, to the /preUpdateUser endpoint of the web server hosted by the tenant.
4. Post Update User - Generates a POST request, after the user is updated, to the /postUpdateUser endpoint of the web server hosted by the tenant.
5. Validate User - Generates a POST request, before the user is created and validation is to be run, to the /validateUser endpoint of the web server hosted by the tenant.
6. Validate Update User - Generates a POST request, before the user is created and validation is to be run, to the /validateUpdateUser endpoint of the web server hosted by the tenant.
7. Change password - Generates a POST request, upon the change of password for a user, to the /changePassword endpoint of the web server hosted by the tenant.
8. Pre Provision - Generates a POST request, before the provisioning of the user to an application, to the /preProvision endpoint of the web server hosted by the tenant.
9. Post Provision - Generates a POST request, after the provisioning of the user to an application, to the /postProvision endpoint of the web server hosted by the tenant.
10. Policy Map - Generates a POST request, while assigning the application to a user, to the /policyMap endpoint of the web server hosted by the tenant.
11. Deprovision Run - Generates a POST request, upon the update of a user to deprovision a user, to the /runDeprovision endpoint of the web server hosted by the tenant.\
    \


While other webhooks operate on a principle of fire-and-forget, the validateUser and the validateUpdateUser expect the response from the tenant as the same or modified body as sent to it for validation.

### API body for the endpoints

&#x20;                                     &#x20;

**Test web hook**&#x20;

Purpose : This api is used to test web hook api.

Input Needed: NA

Curl Request:

curl --location --request POST '[http://192.168.29.227:8080/webhook/test](http://192.168.29.227:8080/webhook/test)' \\

\--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJhZG1pbiIsImRlbGVnYXRlZSI6bnVsbCwiZGVsZWdhdGVlSWQiOm51bGwsImZpcnN0TG9naW4iOmZhbHNlLCJyb2xlcyI6WyJPUkdfQURNSU4iLCJVU0VSIl0sInRlbmFudElkIjoiYXMxMDAiLCJleHAiOjE2NDYzOTYzMDgsInVzZXJJZCI6IjYyMTRkYjdiZDY2MWE1NzM4NmE3MWYxMCIsImlhdCI6MTY0NjM5MDMwOH0.bdKZ3UBCedT91bJAWLCo2AOahIs5ClFMAhnj36f\_ecQ' \\

\--header 'Content-Type: application/json' \\

\--data-raw '{

}'

Response:

{\
"response": {}\
}

&#x20;

**Pre Create User**

Purpose : This web hook api is used to do some events before creating a user in the target system.

Input needed :             &#x20;

{

&#x20;  "request": {

&#x20;      "user": {

&#x20;          "assignedGroups": \[],

&#x20;          "provisionedApps": {},

&#x20;          "securityQuestion": {},

&#x20;          "country": "India",

&#x20;          "firstName": "Shreyash2",

&#x20;          "lastName": "Pande2",

&#x20;          "login": "shreyash2",

&#x20;          "userType": "Employee"

&#x20;      }

&#x20;  }

}

Curl request:

curl --location --request POST '[https://52.66.206.31:8080/webhook/preCreateUser](https://52.66.206.31:8080/webhook/preCreateUser)' \\

\--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJhZG1pbiIsImRlbGVnYXRlZSI6bnVsbCwiZGVsZWdhdGVlSWQiOm51bGwsImZpcnN0TG9naW4iOmZhbHNlLCJyb2xlcyI6WyJPUkdfQURNSU4iLCJVU0VSIl0sInRlbmFudElkIjoiYXMxMDAiLCJleHAiOjE2NDYzOTYzMDgsInVzZXJJZCI6IjYyMTRkYjdiZDY2MWE1NzM4NmE3MWYxMCIsImlhdCI6MTY0NjM5MDMwOH0.bdKZ3UBCedT91bJAWLCo2AOahIs5ClFMAhnj36f\_ecQ' \\

\--header 'Content-Type: application/json' \\

\--data-raw '{

&#x20;   "request": {

&#x20;       "user": {

&#x20;           "assignedGroups": \[],

&#x20;           "provisionedApps": {},

&#x20;           "securityQuestion": {},

&#x20;           "country": "India",

&#x20;           "firstName": "Shreyash2",

&#x20;           "lastName": "Pande2",

&#x20;           "login": "shreyash2",

&#x20;           "userType": "Employee"

&#x20;       }

&#x20;   }

}'\
\


Response: {

&#x20;  "response": {

&#x20;      "data": {

&#x20;          "assignedGroups": \[],

&#x20;          "provisionedApps": {},

&#x20;          "securityQuestion": {},

&#x20;          "country": "India",

&#x20;          "firstName": "Shreyash2",

&#x20;          "lastName": "Pande2",

&#x20;          "login": "shreyash2",

&#x20;          "userType": "Employee"

&#x20;      }

&#x20;  }

}

&#x20;

**Post create User**

Purpose : This web hook is used to do some events after creating a user in the target system.

Curl request: curl --location --request POST '[http://192.168.1.193:8080/webhook/postCreateUser](http://192.168.1.193:8080/webhook/postCreateUser)' \\

\--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJhZG1pbiIsImRlbGVnYXRlZSI6bnVsbCwiZGVsZWdhdGVlSWQiOm51bGwsImZpcnN0TG9naW4iOmZhbHNlLCJyb2xlcyI6WyJPUkdfQURNSU4iLCJVU0VSIl0sInRlbmFudElkIjoiYXMxMDAiLCJleHAiOjE2NDYzOTYzMDgsInVzZXJJZCI6IjYyMTRkYjdiZDY2MWE1NzM4NmE3MWYxMCIsImlhdCI6MTY0NjM5MDMwOH0.bdKZ3UBCedT91bJAWLCo2AOahIs5ClFMAhnj36f\_ecQ' \\

\--header 'Content-Type: application/json' \\

\--data-raw '{

&#x20;   "request": {

&#x20;       "user": {

&#x20;           "assignedGroups": \[],

&#x20;           "provisionedApps": {},

&#x20;           "securityQuestion": {},

&#x20;           "country": "India",

&#x20;           "firstName": "Shreyash2",

&#x20;           "lastName": "Pande2",

&#x20;           "login": "shreyash2",

&#x20;           "userType": "Employee"

&#x20;       }

&#x20;   }

}'

Response : NA

&#x20;

**Restful API - Pre update user**

Purpose : This web hook is used to do some events before updating a user in the target system.

Input needed:&#x20;

{

&#x20;  "request": {

&#x20;      "user": {

&#x20;          "assignedGroups": \[],

&#x20;          "provisionedApps": {},

&#x20;          "securityQuestion": {},

&#x20;          "country": "India",

&#x20;          "firstName": "Shreyash2",

&#x20;          "lastName": "Pande2",

&#x20;          "login": "shreyash2",

&#x20;          "userType": "Employee"

&#x20;      }

&#x20;  }

}

\
\


Curl request:&#x20;

curl --location --request POST '[http://192.168.1.193:8080/webhook/preUpdateUser](http://192.168.1.193:8080/webhook/preUpdateUser)' \\

\--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJhZG1pbiIsImRlbGVnYXRlZSI6bnVsbCwiZGVsZWdhdGVlSWQiOm51bGwsImZpcnN0TG9naW4iOmZhbHNlLCJyb2xlcyI6WyJPUkdfQURNSU4iLCJVU0VSIl0sInRlbmFudElkIjoiYXMxMDAiLCJleHAiOjE2NDYzOTYzMDgsInVzZXJJZCI6IjYyMTRkYjdiZDY2MWE1NzM4NmE3MWYxMCIsImlhdCI6MTY0NjM5MDMwOH0.bdKZ3UBCedT91bJAWLCo2AOahIs5ClFMAhnj36f\_ecQ' \\

\--header 'Content-Type: application/json' \\

\--data-raw '{

&#x20;   "request": {

&#x20;       "user": {

&#x20;           "assignedGroups": \[],

&#x20;           "provisionedApps": {},

&#x20;           "securityQuestion": {},

&#x20;           "country": "India",

&#x20;           "firstName": "Shreyash2",

&#x20;           "lastName": "Pande2",

&#x20;           "login": "shreyash2",

&#x20;           "userType": "Employee"

&#x20;       }

&#x20;   }

}'

\
\


Response

{

&#x20;  "response": {

&#x20;      "data": {

&#x20;          "assignedGroups": \[],

&#x20;          "provisionedApps": {},

&#x20;          "securityQuestion": {},

&#x20;          "country": "India",

&#x20;          "firstName": "Shreyash2",

&#x20;          "lastName": "Pande2",

&#x20;          "login": "shreyash2",

&#x20;          "userType": "Employee"

&#x20;      }

&#x20;  }

}

&#x20;

**Post update user**

Purpose : This web hook is used to do some events after updating a user in the target system.

Input needed :

{

&#x20;  "request": {

&#x20;      "user": {

&#x20;          "assignedGroups": \[],

&#x20;          "provisionedApps": {},

&#x20;          "securityQuestion": {},

&#x20;          "country": "India",

&#x20;          "firstName": "Shreyash2",

&#x20;          "lastName": "Pande2",

&#x20;          "login": "shreyash2",

&#x20;          "userType": "Employee"

&#x20;      }

&#x20;  }

}

\
Curl request:

curl --location --request POST '[http://192.168.1.193:8080/webhook/postUpdateUser](http://192.168.1.193:8080/webhook/postUpdateUser)' \\

\--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJhZG1pbiIsImRlbGVnYXRlZSI6bnVsbCwiZGVsZWdhdGVlSWQiOm51bGwsImZpcnN0TG9naW4iOmZhbHNlLCJyb2xlcyI6WyJPUkdfQURNSU4iLCJVU0VSIl0sInRlbmFudElkIjoiYXMxMDAiLCJleHAiOjE2NDYzOTYzMDgsInVzZXJJZCI6IjYyMTRkYjdiZDY2MWE1NzM4NmE3MWYxMCIsImlhdCI6MTY0NjM5MDMwOH0.bdKZ3UBCedT91bJAWLCo2AOahIs5ClFMAhnj36f\_ecQ' \\

\--header 'Content-Type: application/json' \\

\--data-raw '{

&#x20;   "request": {

&#x20;       "user": {

&#x20;           "assignedGroups": \[],

&#x20;           "provisionedApps": {},

&#x20;           "securityQuestion": {},

&#x20;           "country": "India",

&#x20;           "firstName": "Shreyash2",

&#x20;           "lastName": "Pande2",

&#x20;           "login": "shreyash2",

&#x20;           "userType": "Employee"

&#x20;       }

&#x20;   }

}'

\
\


Response:  NA

&#x20;

&#x20;**Validate User**&#x20;

Purpose : This web hook is used to validate users before creating  a user in the target system.

Input Needed :

{

&#x20;  "request": {

&#x20;      "user": {

&#x20;          "assignedGroups": \[],

&#x20;          "provisionedApps": {},

&#x20;          "securityQuestion": {},

&#x20;          "country": "India",

&#x20;          "firstName": "Shreyash2",

&#x20;          "lastName": "Pande2",

&#x20;          "login": "shreyash2",

&#x20;          "userType": "Employee"

&#x20;      }

&#x20;  }

}

Curl request: curl --location --request POST '[http://192.168.1.193:8080/webhook/validateUser](http://192.168.1.193:8080/webhook/validateUser)' \\

\--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJhZG1pbiIsImRlbGVnYXRlZSI6bnVsbCwiZGVsZWdhdGVlSWQiOm51bGwsImZpcnN0TG9naW4iOmZhbHNlLCJyb2xlcyI6WyJPUkdfQURNSU4iLCJVU0VSIl0sInRlbmFudElkIjoiYXMxMDAiLCJleHAiOjE2NDYzOTYzMDgsInVzZXJJZCI6IjYyMTRkYjdiZDY2MWE1NzM4NmE3MWYxMCIsImlhdCI6MTY0NjM5MDMwOH0.bdKZ3UBCedT91bJAWLCo2AOahIs5ClFMAhnj36f\_ecQ' \\

\--header 'Content-Type: application/json' \\

\--data-raw '{

&#x20;   "request": {

&#x20;       "user": {

&#x20;           "assignedGroups": \[],

&#x20;           "provisionedApps": {},

&#x20;           "securityQuestion": {},

&#x20;           "country": "India",

&#x20;           "firstName": "Shreyash2",

&#x20;           "lastName": "Pande2",

&#x20;           "login": "shreyash2",

&#x20;           "userType": "Employee"

&#x20;       }

&#x20;   }

}'

&#x20;

Response: {

&#x20;  "response": {

&#x20;      "error": true,

&#x20;      "message": "MobileAlreadyExist"

&#x20;  }

}

\
\


**Validate update user**&#x20;

Purpose : This web hook is used to validate users before updating  a user in the target system.

Input needed:&#x20;

&#x20;  "request": {

&#x20;      "user": {

&#x20;          "assignedGroups": \[],

&#x20;          "provisionedApps": {},

&#x20;          "securityQuestion": {},

&#x20;          "country": "India",

&#x20;          "firstName": "Shreyash2",

&#x20;          "lastName": "Pande2",

&#x20;          "login": "shreyash2",

&#x20;          "userType": "Employee"

&#x20;      }

&#x20;  }

}

\
\


Curl request:&#x20;

curl --location --request POST '[http://192.168.1.193:8080/webhook/validateUpdateUser](http://192.168.1.193:8080/webhook/validateUpdateUser)' \\

\--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJhZG1pbiIsImRlbGVnYXRlZSI6bnVsbCwiZGVsZWdhdGVlSWQiOm51bGwsImZpcnN0TG9naW4iOmZhbHNlLCJyb2xlcyI6WyJPUkdfQURNSU4iLCJVU0VSIl0sInRlbmFudElkIjoiYXMxMDAiLCJleHAiOjE2NDYzOTYzMDgsInVzZXJJZCI6IjYyMTRkYjdiZDY2MWE1NzM4NmE3MWYxMCIsImlhdCI6MTY0NjM5MDMwOH0.bdKZ3UBCedT91bJAWLCo2AOahIs5ClFMAhnj36f\_ecQ' \\

\--header 'Content-Type: application/json' \\

\--data-raw '{

&#x20;   "request": {

&#x20;       "user": {

&#x20;           "assignedGroups": \[],

&#x20;           "provisionedApps": {},

&#x20;           "securityQuestion": {},

&#x20;           "country": "India",

&#x20;           "firstName": "Shreyash2",

&#x20;           "lastName": "Pande2",

&#x20;           "login": "shreyash2",

&#x20;           "userType": "Employee"

&#x20;       }

&#x20;   }

}'

Response:

{

&#x20;  "response": {

&#x20;      "error": true,

&#x20;      "message": "EmailAlreadyExist"

&#x20;  }

}

&#x20;

**Change password**

Purpose : This web hook is used to do some events on password change.

Input Needed :

{

&#x20;  "request": {

&#x20;      "user": {

&#x20;          "assignedGroups": \[],

&#x20;          "provisionedApps": {},

&#x20;          "securityQuestion": {},

&#x20;          "country": "India",

&#x20;          "firstName": "Shreyash2",

&#x20;          "lastName": "Pande2",

&#x20;          "login": "shreyash2",

&#x20;          "userType": "Employee"

&#x20;      },

&#x20;      "passwordText" : "Welcome@123"

&#x20;  }

}

\
\


Curl request: curl --location --request POST '[http://192.168.1.193:8080/webhook/changePassword](http://192.168.1.193:8080/webhook/changePassword)' \\

\--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJhZG1pbiIsImRlbGVnYXRlZSI6bnVsbCwiZGVsZWdhdGVlSWQiOm51bGwsImZpcnN0TG9naW4iOmZhbHNlLCJyb2xlcyI6WyJPUkdfQURNSU4iLCJVU0VSIl0sInRlbmFudElkIjoiYXMxMDAiLCJleHAiOjE2NDYzOTYzMDgsInVzZXJJZCI6IjYyMTRkYjdiZDY2MWE1NzM4NmE3MWYxMCIsImlhdCI6MTY0NjM5MDMwOH0.bdKZ3UBCedT91bJAWLCo2AOahIs5ClFMAhnj36f\_ecQ' \\

\--header 'Content-Type: application/json' \\

\--data-raw '{

&#x20;   "request": {

&#x20;       "user": {

&#x20;           "assignedGroups": \[],

&#x20;           "provisionedApps": {},

&#x20;           "securityQuestion": {},

&#x20;           "country": "India",

&#x20;           "firstName": "Shreyash2",

&#x20;           "lastName": "Pande2",

&#x20;           "login": "shreyash2",

&#x20;           "userType": "Employee"

&#x20;       },

&#x20;       "passwordText" : "Welcome@123"

&#x20;   }

}'

\
Response: NA

&#x20;

**Pre provision**

\
Purpose : This web hook is used to do some events before assigning applications to a user.

Input Needed :

{

&#x20;  "request": {

&#x20;      "policyMap" : "email",

&#x20;      "form" : "",

&#x20;      "applicationId" : "620231fee789224ec1cec3dd",

&#x20;      "roleList" : \[],

&#x20;      "action" : "Application Create",

&#x20;       "user": {

&#x20;          "assignedGroups": \[],

&#x20;          "provisionedApps": {},

&#x20;          "securityQuestion": {},

&#x20;          "country": "India",

&#x20;          "firstName": "Shreyash2",

&#x20;          "lastName": "Pande2",

&#x20;          "login": "shreyash2",

&#x20;          "userType": "Employee"

&#x20;      }

&#x20;

&#x20;  }

}

&#x20;

Curl Request:

curl --location --request POST '[http://192.168.1.193:8080/webhook/preProvision](http://192.168.1.193:8080/webhook/preProvision)' \\

\--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJhZG1pbiIsImRlbGVnYXRlZSI6bnVsbCwiZGVsZWdhdGVlSWQiOm51bGwsImZpcnN0TG9naW4iOmZhbHNlLCJyb2xlcyI6WyJPUkdfQURNSU4iLCJVU0VSIl0sInRlbmFudElkIjoiYXMxMDAiLCJleHAiOjE2NDYzOTYzMDgsInVzZXJJZCI6IjYyMTRkYjdiZDY2MWE1NzM4NmE3MWYxMCIsImlhdCI6MTY0NjM5MDMwOH0.bdKZ3UBCedT91bJAWLCo2AOahIs5ClFMAhnj36f\_ecQ' \\

\--header 'Content-Type: application/json' \\

\--data-raw '{

&#x20;   "request": {

&#x20;       "policyMap" : "email",

&#x20;       "form" : "",

&#x20;       "applicationId" : "620231fee789224ec1cec3dd",

&#x20;       "roleList" : \[],

&#x20;       "action" : "Application Create",

&#x20;        "user": {

&#x20;           "assignedGroups": \[],

&#x20;           "provisionedApps": {},

&#x20;           "securityQuestion": {},

&#x20;           "country": "India",

&#x20;           "firstName": "Shreyash2",

&#x20;           "lastName": "Pande2",

&#x20;           "login": "shreyash2",

&#x20;           "userType": "Employee"

&#x20;       }

&#x20;

&#x20;   }

}'

&#x20;

Response : NA

&#x20;

&#x20;**Post provision**

Purpose : This web hook is used to do some events after assigning applications to a user.

**Input Needed :**

{

&#x20;  "request": {

&#x20;      "policyMap" : "email",

&#x20;      "form" : "",

&#x20;      "applicationId" : "620231fee789224ec1cec3dd",

&#x20;      "roleList" : \[],

&#x20;      "action" : "Application Create",

&#x20;       "user": {

&#x20;          "assignedGroups": \[],

&#x20;          "provisionedApps": {},

&#x20;          "securityQuestion": {},

&#x20;          "country": "India",

&#x20;          "firstName": "Shreyash2",

&#x20;          "lastName": "Pande2",

&#x20;          "login": "shreyash2",

&#x20;          "userType": "Employee"

&#x20;      },

&#x20;      "isSuccess" : **true**,

&#x20;      "uid" : "5f36283bc193991db0990d3e"

&#x20;  }

}

&#x20;

Curl response :

curl --location --request POST '[http://192.168.1.193:8080/webhook/postProvision](http://192.168.1.193:8080/webhook/postProvision)' \\

\--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJhZG1pbiIsImRlbGVnYXRlZSI6bnVsbCwiZGVsZWdhdGVlSWQiOm51bGwsImZpcnN0TG9naW4iOmZhbHNlLCJyb2xlcyI6WyJPUkdfQURNSU4iLCJVU0VSIl0sInRlbmFudElkIjoiYXMxMDAiLCJleHAiOjE2NDYzOTYzMDgsInVzZXJJZCI6IjYyMTRkYjdiZDY2MWE1NzM4NmE3MWYxMCIsImlhdCI6MTY0NjM5MDMwOH0.bdKZ3UBCedT91bJAWLCo2AOahIs5ClFMAhnj36f\_ecQ' \\

\--header 'Content-Type: application/json' \\

\--data-raw '{

&#x20;   "request": {

&#x20;       "policyMap" : "email",

&#x20;       "form" : "",

&#x20;       "applicationId" : "620231fee789224ec1cec3dd",

&#x20;       "roleList" : \[],

&#x20;       "action" : "Application Create",

&#x20;        "user": {

&#x20;           "assignedGroups": \[],

&#x20;           "provisionedApps": {},

&#x20;           "securityQuestion": {},

&#x20;           "country": "India",

&#x20;           "firstName": "Shreyash2",

&#x20;           "lastName": "Pande2",

&#x20;           "login": "shreyash2",

&#x20;           "userType": "Employee"

&#x20;       },

&#x20;       "isSuccess" : true,

&#x20;       "uid" : "5f36283bc193991db0990d3e"

&#x20;   }

}'

&#x20;

Response : NA

&#x20;

&#x20;

**Policy map**

Purpose : This web hook is used to do some events on policy map while assigning the application to a user.

Input needed :&#x20;

&#x20;  "request": {

&#x20;      "targetAttribute" : "email",

&#x20;      "cymmetrifield" : "email",

&#x20;       "defaultValue" : "[example@gmail.com](mailto:example@gmail.com)",

&#x20;      "formVeriable" : "",

&#x20;      "user": {

&#x20;          "assignedGroups": \[],

&#x20;          "provisionedApps": {},

&#x20;          "securityQuestion": {},

&#x20;          "country": "India",

&#x20;          "firstName": "Shreyash2",

&#x20;          "lastName": "Pande2",

&#x20;          "login": "shreyash2",

&#x20;          "userType": "Employee"

&#x20;      }

&#x20;  }

}

\
\


Curl request :

curl --location --request POST '[https://52.66.206.31:8080/webhook/policymap](https://52.66.206.31:8080/webhook/policymap)' \\

\--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJhZG1pbiIsImRlbGVnYXRlZSI6bnVsbCwiZGVsZWdhdGVlSWQiOm51bGwsImZpcnN0TG9naW4iOmZhbHNlLCJyb2xlcyI6WyJPUkdfQURNSU4iLCJVU0VSIl0sInRlbmFudElkIjoiYXMxMDAiLCJleHAiOjE2NDYzOTYzMDgsInVzZXJJZCI6IjYyMTRkYjdiZDY2MWE1NzM4NmE3MWYxMCIsImlhdCI6MTY0NjM5MDMwOH0.bdKZ3UBCedT91bJAWLCo2AOahIs5ClFMAhnj36f\_ecQ' \\

\--header 'Content-Type: application/json' \\

\--data-raw '{

&#x20;   "request": {

&#x20;       "targetAttribute" : "email",

&#x20;       "cymmetrifield" : "email",

&#x20;        "defaultValue" : "[example@gmail.com](mailto:example@gmail.com)",

&#x20;       "formVeriable" : "",

&#x20;       "user": {

&#x20;           "assignedGroups": \[],

&#x20;           "provisionedApps": {},

&#x20;           "securityQuestion": {},

&#x20;           "country": "India",

&#x20;           "firstName": "Shreyash2",

&#x20;           "lastName": "Pande2",

&#x20;           "login": "shreyash2",

&#x20;           "userType": "Employee"

&#x20;       }

&#x20;   }

}'

\
\


Response :&#x20;

{

&#x20;  "response": {

&#x20;      "mappedValue": "valid"

&#x20;  }

}

&#x20;

**Run deprovisioning**

Purpose : This web hook is used for deprovisioning applications when users get updated .

\
Input needed :&#x20;

{

&#x20;  "request": {

&#x20;      "user": {

&#x20;          "assignedGroups": \[],

&#x20;          "provisionedApps": {},

&#x20;          "securityQuestion": {},

&#x20;          "country": "India",

&#x20;          "firstName": "Shreyash2",

&#x20;          "lastName": "Pande2",

&#x20;          "login": "shreyash2",

&#x20;          "userType": "Employee"

&#x20;      }

&#x20;  }

}

&#x20;

Curl request:&#x20;

curl --location --request POST '[https://52.66.206.31:8080/webhook/runDeprovision](https://52.66.206.31:8080/webhook/runDeprovision)' \\

\--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJhZG1pbiIsImRlbGVnYXRlZSI6bnVsbCwiZGVsZWdhdGVlSWQiOm51bGwsImZpcnN0TG9naW4iOmZhbHNlLCJyb2xlcyI6WyJPUkdfQURNSU4iLCJVU0VSIl0sInRlbmFudElkIjoiYXMxMDAiLCJleHAiOjE2NDYzOTYzMDgsInVzZXJJZCI6IjYyMTRkYjdiZDY2MWE1NzM4NmE3MWYxMCIsImlhdCI6MTY0NjM5MDMwOH0.bdKZ3UBCedT91bJAWLCo2AOahIs5ClFMAhnj36f\_ecQ' \\

\--header 'Content-Type: application/json' \\

\--data-raw '{

&#x20;   "request": {

&#x20;       "user": {

&#x20;           "assignedGroups": \[],

&#x20;           "provisionedApps": {},

&#x20;           "securityQuestion": {},

&#x20;           "country": "India",

&#x20;           "firstName": "Shreyash2",

&#x20;           "lastName": "Pande2",

&#x20;           "login": "shreyash2",

&#x20;           "userType": "Employee"

&#x20;       }

&#x20;   }

}'

&#x20;

Response:

{

&#x20;  "response": {

&#x20;      "data": true

&#x20;  }

}
