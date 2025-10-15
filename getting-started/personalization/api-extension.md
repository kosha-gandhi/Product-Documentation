---
description: >-
  Cymmetri framework to extend the out of box use cases and support custom
  requirements from the platform
---

# API Extension

### Reference API calls <a href="#id-1d6m2h68bkie" id="id-1d6m2h68bkie"></a>

The following are the APIs calls.

**Important Note:**

### RESTful API – Assigned application search user <a href="#id-3l075l2oyx6c" id="id-3l075l2oyx6c"></a>

**Purpose:** This API is used to create an application hook

**URL: http://\<tenant\_domain>/api/user/listByApplication**

**Method: POST**

**Example Request:**

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>curl --location --request POST 'http://api.cymmetri.in/usersrvc/api/user/listByApplication' \</p><p>--header 'Content-Type: application/json' \</p><p>--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJhZG1pbiIsImRlbGVnYXRlZSI6bnVsbCwiZGVsZWdhdGVlSWQiOm51bGwsImZpcnN0TG9naW4iOmZhbHNlLCJyb2xlcyI6WyJPUkdfQURNSU4iLCJVU0VSIl0sInRlbmFudElkIjoiZ2s0MCIsImV4cCI6MTY0NzAxNzEwNywidXNlcklkIjoiNjE3MDE1YTNjMDQ4MTc1NmI3OThhY2EyIiwiaWF0IjoxNjQ3MDExMTA3fQ.8j711_L--eQHHfen2GPI1qWCmUWRd4n6O44HCZhuRSo' \</p><p>--data-raw '{</p><p>    "keyword":"shu",</p><p>    "pageNumber": "0",</p><p>    "pageSize": "10",</p><p>    "filter": {</p><p>        "applicationId": "617253cc2fb4b2125b237b75"</p><p>    },</p><p>    "sortDirection": "ASC",</p><p>    "sortOn": [</p><p>        "id"</p><p>    ]</p><p>}'</p><p> </p> |

**Sample Response:**

**On success:**

`{`

`"success": true,`

`"data": {`

`"content": [`

`{`

`"id": "619ce9a69139ca14885a4717",`

`"displayName": "John Snow",`

`"firstName": "John",`

`"lastName": "Snow",`

`"email": null,`

`"mobile": null,`

`"designation": "Developer",`

`"status": "ACTIVE",`

`"profilePic": null,`

`"login": "john.snow",`

`"initialLoginPending": true,`

`"startDate": null,`

`"endDate": null,`

`"provStatus": {`

`"617253cc2fb4b2125b237b75": "SUCCESS_UPDATE"`

`}`

`}`

`],`

`"pageable": {`

`"sort": [`

`{`

`"direction": "ASC",`

`"property": "id",`

`"ignoreCase": false,`

`"nullHandling": "NATIVE",`

`"ascending": true,`

`"descending": false`

`}`

`],`

`"pageNumber": 0,`

`"pageSize": 10,`

`"offset": 0,`

`"paged": true,`

`"unpaged": false`

`},`

`"last": true,`

`"totalPages": 1,`

`"totalElements": 1,`

`"sort": [`

`{`

`"direction": "ASC",`

`"property": "id",`

`"ignoreCase": false,`

`"nullHandling": "NATIVE",`

`"ascending": true,`

`"descending": false`

`}`

`],`

`"first": true,`

`"number": 0,`

`"numberOfElements": 1,`

`"size": 10,`

`"empty": false`

`},`

`"timestamp": "02-Mar-2022 01:58:57",`

`"message": null,`

`"errorCode": null`

`}`

**`On failure:`**

**`Response 1#`**

`{`

`"data":`` `**`null`**`,`

`"success":`` `**`false`**`,`

`"errorCode": "PROVSRVC.APPLICATION_NOT_FOUND",`

`"message":`` `**`null`**`,`

`"timestamp": "02-Mar-2022 01:59:39"`

`}`

### RESTful API – Assigned application search group <a href="#pcql2x4ovudj" id="pcql2x4ovudj"></a>

**Purpose:** This API is used to get an application hook for the provided application id and type.

**URL: http://\<tenant\_domain>/api/group/groupListByApplication**

**Method: POST**

**applicationId: Application id**

**Example Request:**

| <p>curl --location --request POST 'http://localhost:9080/api/group/groupListByApplication' \</p><p>--header 'Tenant: gk16'</p><p>--data-raw '{</p><p>   "filter": {</p><p>       "applicationId": "617253cc2fb4b2125b237b75"</p><p>   },</p><p>   "keyword": "gold",</p><p>   "pageNumber": 0,</p><p>   "pageSize": 10,</p><p>   "sortDirection": "ASC",</p><p>   "sortOn": [</p><p>       "name"</p><p>   ]</p><p>}'</p> |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

**Sample Response:**

**On success:**

`{`

`"success": true,`

`"data": {`

`"offset": 0,`

`"pageSize": 10,`

`"totalElements": 1,`

`"totalPages": 1,`

`"elements": [`

`{`

`"id": "621cdbb7776c95564c0313ab",`

`"name": "Gold",`

`"type": "LocalGroup",`

`"description": "Gold group",`

`"ouId": "",`

`"ouName": null,`

`"parentGroupIds": null,`

`"directParentGroupId": null,`

`"userCount": 0,`

`"appCount": 1`

`}`

`],`

`"pageNumber": 0,`

`"sort": {`

`"orders": [`

`{`

`"direction": "ASC",`

`"property": "name"`

`}`

`],`

`"sorted": true`

`}`

`},`

`"timestamp": "03-Mar-2022 05:29:23",`

`"message": null,`

`"errorCode": null`

`}`

**On failure:**

**Response 1#**

`{`

`"data":`` `**`null`**`,`

`"success":`` `**`false`**`,`

`"errorCode": "PROVSRVC.APPLICATION_NOT_FOUND",`

`"message":`` `**`null`**`,`

`"timestamp": "03-Mar-2022 05:29:49"`

`}`

### RESTful API – Application reconciliation pull filter search <a href="#i0xgmz2qxrtb" id="i0xgmz2qxrtb"></a>

**Purpose:** This API is used to list reconciliation pulls for the provided application ID and keyword.

**URL: https://\<tenant\_domain>/provsrvc/reconciliation/pull/search**

**Method: POST**

**applicationId: applicationId**

**keyword: keyword**

**Example Request:**

|                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>curl --location --request POST 'https://mru18.cymmetri.in/provsrvc/reconciliation/pull/search' \</p><p>--header 'Tenant: mru18' \</p><p>--data-raw '{</p><p>    "filter": {</p><p>        "applicationId": "614b5d3489ad96554e89e2ab"</p><p>    },</p><p>    "keyword": "",</p><p>    "pageNumber": 0,</p><p>    "pageSize": 10,</p><p>    "sortDirection": "DESC",</p><p>    "sortOn": [</p><p>        "updatedDateTime"</p><p>    ]</p><p>}'</p> |
|                                                                                                                                                                                                                                                                                                                                                                                                                                                       |

**Sample Response:**

**On success:**

`{`

`"success": true,`

`"data": {`

`"content": [`

`{`

`"id": "621cca3f9423002d41cbbed4",`

`"name": "AD-ADMIN-USERS",`

`"type": "USER",`

`"status": "ACTIVE",`

`"applicationId": "614b5d3489ad96554e89e2ab",`

`"targetSystemSearchQueryFilter": null,`

`"idmRepositoryField": "login",`

`"sourceAttributeName": "cn",`

`"reconType": "PULL",`

`"reconMode": "FILTERED_RECONCILIATION",`

`"reconConditions": {`

`"TARGET_DELETED_IDM_EXISTS": "IGNORE",`

`"TARGET_EXTSTS_IDM_EXISTS": "IGNORE",`

`"TARGET_EXTSTS_IDM_NOT_EXISTS": "PROVISION"`

`},`

`"lastRunDateTime": null,`

`"createdDateTime": "2022-02-28T13:12:31.07",`

`"updatedDateTime": "2022-03-02T12:45:31.069",`

`"version": 2`

`},`

`...`

`...`

`],`

`"pageable": {`

`"sort": [`

`{`

`"direction": "DESC",`

`"property": "updatedDateTime",`

`"ignoreCase": false,`

`"nullHandling": "NATIVE",`

`"ascending": false,`

`"descending": true`

`}`

`],`

`"pageNumber": 0,`

`"pageSize": 10,`

`"offset": 0,`

`"paged": true,`

`"unpaged": false`

`},`

`"last": true,`

`"totalPages": 1,`

`"totalElements": 3,`

`"first": true,`

`"sort": [`

`{`

`"direction": "DESC",`

`"property": "updatedDateTime",`

`"ignoreCase": false,`

`"nullHandling": "NATIVE",`

`"ascending": false,`

`"descending": true`

`}`

`],`

`"numberOfElements": 3,`

`"size": 10,`

`"number": 0,`

`"empty": false`

`},`

`"timestamp": "03-Mar-2022 08:41:03",`

`"message": null,`

`"errorCode": null`

`}`

**On failure:**

**Response 1#**

`{`

`"success": false,`

`"data": null,`

`"timestamp": "03-Mar-2022 09:06:43",`

`"message": null,`

`"errorCode": "INVALID_ARGUMENTS"`

`}`

**Response 2#**

`{`

`"success": false,`

`"data": null,`

`"timestamp": "03-Mar-2022 09:06:43",`

`"message": null,`

`"errorCode": "PROVSRVC.UNKNOWN"`

`}`

### RESTful API – Application reconciliation push filter search <a href="#oozxve3hcfpr" id="oozxve3hcfpr"></a>

**Purpose:** This API is used to list reconciliation push for provided application id and keyword.

**URL: http://\<tenant\_domain>/reconciliation/push/search**

**Method: POST**

**applicationId: Application Id.**

**keyword : keyword**

**Example Request:**

|                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>curl --location --request POST 'https://mru18.cymmetri.in/provsrvc/reconciliation/pull/search' \</p><p>--header 'Tenant: mru18' \</p><p>--data-raw '{</p><p>    "filter": {</p><p>        "applicationId": "614b5d3489ad96554e89e2ab"</p><p>    },</p><p>    "keyword": "",</p><p>    "pageNumber": 0,</p><p>    "pageSize": 10,</p><p>    "sortDirection": "DESC",</p><p>    "sortOn": [</p><p>        "updatedDateTime"</p><p>    ]</p><p>}'</p> |

**Sample Response:**

**On success:**

`{`

`"success": true,`

`"data": {`

`"content": [`

`{`

`"id": "62207b1655a2d10f525dc2bf",`

`"name": "AD-Admin",`

`"type": "USER",`

`"status": "ACTIVE",`

`"applicationId": "614b5d3489ad96554e89e2ab",`

`"idmSearchQueryFilter": {`

`"location": null,`

`"reportingManager": null,`

`"department": null,`

`"designation": null,`

`"group": null,`

`"email": null,`

`"mobile": null,`

`"status": [],`

`"userType": null,`

`"locked": false`

`},`

`"idmRepositoryField": "login",`

`"sourceAttributeName": "cn",`

`"reconType": "PUSH",`

`"reconMode": "FILTERED_RECONCILIATION",`

`"reconConditions": {`

`"IDM_DELETED_TARGET_EXISTS": "IGNORE",`

`"IDM_EXTSTS_TARGET_EXISTS": "IGNORE",`

`"IDM_EXTSTS_TARGET_NOT_EXISTS": "PROVISION"`

`},`

`"lastRunDateTime": null,`

`"createdDateTime": "2022-03-03T08:23:50.963",`

`"updatedDateTime": "2022-03-03T08:23:50.963",`

`"version": 0`

`}`

`…`

`…`

`],`

`"pageable": {`

`"sort": [`

`{`

`"direction": "DESC",`

`"property": "updatedDateTime",`

`"ignoreCase": false,`

`"nullHandling": "NATIVE",`

`"ascending": false,`

`"descending": true`

`}`

`],`

`"pageNumber": 0,`

`"pageSize": 10,`

`"offset": 0,`

`"paged": true,`

`"unpaged": false`

`},`

`"last": true,`

`"totalPages": 1,`

`"totalElements": 3,`

`"first": true,`

`"sort": [`

`{`

`"direction": "DESC",`

`"property": "updatedDateTime",`

`"ignoreCase": false,`

`"nullHandling": "NATIVE",`

`"ascending": false,`

`"descending": true`

`}`

`],`

`"numberOfElements": 3,`

`"size": 10,`

`"number": 0,`

`"empty": false`

`},`

`"timestamp": "03-Mar-2022 08:40:09",`

`"message": null,`

`"errorCode": null`

`}`

**On failure:**

**Response 1#**

`{`

`"success": false,`

`"data": null,`

`"timestamp": "03-Mar-2022 09:06:43",`

`"message": null,`

`"errorCode": "INVALID_ARGUMENTS"`

`}`

**Response 2#**

`{`

`"success": false,`

`"data": null,`

`"timestamp": "03-Mar-2022 09:06:43",`

`"message": null,`

`"errorCode": "PROVSRVC.UNKNOWN"`

`}`

### RESTful API – Application role filter search <a href="#rxuqpye2qdhx" id="rxuqpye2qdhx"></a>

**Purpose:** This API is used to list application roles with provided application id and keyword.

**URL: http://\<tenant\_domain>/applicationRole/findAppRolesByApplicationId**

**Method: POST**

**application id: applicationId**

**keyword: keyword**

**Example Request:**

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>curl --location --request POST 'https://mru18.cymmetri.in/provsrvc/applicationRole/findAppRolesByApplicationId' \</p><p>--header 'Tenant: mru18' \</p><p>--data-raw '{</p><p>    "filter": {</p><p>        "active": true,</p><p>        "applicationId": "614b5d3489ad96554e89e2ab"</p><p>    },</p><p>    "keyword": "",</p><p>    "pageNumber": 0,</p><p>    "pageSize": 10,</p><p>    "sortDirection": "ASC",</p><p>    "sortOn": [</p><p>        "id"</p><p>    ]</p><p>}'</p> |

**Sample Response:**

**On success:**

`{`

`"success": true,`

`"data": {`

`"content": [`

`{`

`"id": "621f2996a36e574d3e7ab4a7",`

`"roleId": "ROLE_ID_101",`

`"roleName": "ADMIN",`

`"roleDescreption": "This role is for admin users.",`

`"applicationId": "614b5d3489ad96554e89e2ab",`

`"cosoType": "Admin",`

`"active": false,`

`"mappedBusinessRoles": [],`

`"createdDateTime": "2022-03-02T08:23:50.608",`

`"updatedDateTime": "2022-03-02T13:48:54.189",`

`"version": 3`

`},`

`...`

`...`

`],`

`"pageable": {`

`"sort": [`

`{`

`"direction": "ASC",`

`"property": "id",`

`"ignoreCase": false,`

`"nullHandling": "NATIVE",`

`"ascending": true,`

`"descending": false`

`}`

`],`

`"pageNumber": 0,`

`"pageSize": 10,`

`"offset": 0,`

`"paged": true,`

`"unpaged": false`

`},`

`"last": true,`

`"totalPages": 1,`

`"totalElements": 3,`

`"first": true,`

`"sort": [`

`{`

`"direction": "ASC",`

`"property": "id",`

`"ignoreCase": false,`

`"nullHandling": "NATIVE",`

`"ascending": true,`

`"descending": false`

`}`

`],`

`"numberOfElements": 3,`

`"size": 10,`

`"number": 0,`

`"empty": false`

`},`

`"timestamp": "03-Mar-2022 09:20:03",`

`"message": null,`

`"errorCode": null`

`}`

**On failure:**

**Response 1#**

`{`

`"success": false,`

`"data": null,`

`"timestamp": "03-Mar-2022 09:06:43",`

`"message": null,`

`"errorCode": "INVALID_ARGUMENTS"`

`}`

**Response 2#**

`{`

`"success": false,`

`"data": null,`

`"timestamp": "03-Mar-2022 09:06:43",`

`"message": null,`

`"errorCode": "PROVSRVC.UNKNOWN"`

`}`

### RESTful API – Application Policy Map filter search <a href="#toim3k6lghhz" id="toim3k6lghhz"></a>

**Purpose:** This API is used to search PolicymapTenant.

**URL: http://\<tenant\_domain>/policyMapTenant/findAll**

**Method: POST**

**tenantApplicationId: Tenant Application Id**

**objectType: Mapping Object Type**

**internal: Internal Attribute**

**external: External Application Attribute**

**Example Request:**

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <p>curl --location --request POST 'api.cymmetri.in/provsrvc/policyMapTenant/findAll' \</p><p>--data-raw '{</p><p>            "keyword": "lastName",</p><p>            "pageNumber": 0,</p><p>            "pageSize": 10,</p><p>            "filter": {</p><p>            "tenantApplicationId": "61dd1da8db654e41881b5273",</p><p>            "objectType": "USER"</p><p>            },</p><p>            "sortDirection": "DESC",</p><p>            "sortOn": [</p><p>            "internal"</p><p>            ]</p><p>}'</p> |

**Sample Response:**

**On success:**

`{`

`"success": true,`

`"data": {`

`"content": [`

`{`

`"id": "61dd1da8db654e41881b5281",`

`"internal": "lastName",`

`"external": "sn",`

`"mandatory": false,`

`"script": null,`

`"createdDateTime": "2022-01-11T06:03:20.202",`

`"updatedDateTime": "2022-01-11T06:03:20.202",`

`"version": 0,`

`"default_val": "",`

`"tenant_applicationId": "61dd1da8db654e41881b5273",`

`"object_type": "USER",`

`"isCustom": false,`

`"scriptEnable": false`

`}`

`],`

`"pageable": {`

`"sort": [`

`{`

`"direction": "DESC",`

`"property": "internal",`

`"ignoreCase": false,`

`"nullHandling": "NATIVE",`

`"ascending": false,`

`"descending": true`

`}`

`],`

`"pageNumber": 0,`

`"pageSize": 10,`

`"offset": 0,`

`"paged": true,`

`"unpaged": false`

`},`

`"last": true,`

`"totalPages": 1,`

`"totalElements": 1,`

`"first": true,`

`"sort": [`

`{`

`"direction": "DESC",`

`"property": "internal",`

`"ignoreCase": false,`

`"nullHandling": "NATIVE",`

`"ascending": false,`

`"descending": true`

`}`

`],`

`"numberOfElements": 1,`

`"size": 10,`

`"number": 0,`

`"empty": false`

`},`

`"timestamp": "03-Mar-2022 07:13:09",`

`"message": null,`

`"errorCode": null`

`}`



### RESTful API – App description in selfservice application list API <a href="#kibsdjse253b" id="kibsdjse253b"></a>

**Purpose:** This API is used to get paginated lists with filters.

**URL: https://\<tenant\_domain>/selfservice/api/selfservice/applications**

**Method: POST**

**Example Request:**

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>curl --location --request POST 'https://gk40.cymmetri.in/selfservice/api/selfservice/applications' \</p><p>--header 'Connection: keep-alive' \</p><p>--header 'Pragma: no-cache' \</p><p>--header 'Cache-Control: no-cache' \</p><p>--header 'sec-ch-ua: " Not A;Brand";v="99", "Chromium";v="96", "Google Chrome";v="96"' \</p><p>--header 'Accept: application/json' \</p><p>--header 'content-type: application/json' \</p><p>--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJhZG1pbiIsImRlbGVnYXRlZSI6bnVsbCwiZGVsZWdhdGVlSWQiOm51bGwsImZpcnN0TG9naW4iOmZhbHNlLCJyb2xlcyI6WyJPUkdfQURNSU4iLCJVU0VSIl0sInRlbmFudElkIjoiZ2s0MCIsImV4cCI6MTY0NzAxNDY2NywidXNlcklkIjoiNjE3MDE1YTNjMDQ4MTc1NmI3OThhY2EyIiwiaWF0IjoxNjQ3MDA4NjY3fQ.jP2BgjiOVUcdxhImVvdwy18puEylWSSOVHnWA_2hhJU' \</p><p>--header 'sec-ch-ua-mobile: ?0' \</p><p>--header 'User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/96.0.4664.45 Safari/537.36' \</p><p>--header 'sec-ch-ua-platform: "Linux"' \</p><p>--header 'Origin: https://gk40.cymmetri.in' \</p><p>--header 'Sec-Fetch-Site: same-origin' \</p><p>--header 'Sec-Fetch-Mode: cors' \</p><p>--header 'Sec-Fetch-Dest: empty' \</p><p>--header 'Referer: https://gk40.cymmetri.in/' \</p><p>--header 'Accept-Language: en-GB,en-US;q=0.9,en;q=0.8' \</p><p>--header 'Cookie: deviceId=6e4caedd-beaf-444c-9312-21b219bb3709; Correlation=B194B86832FB4683ABC43EA6077944E2; Correlation=1E83B306404E4E46A2F6BE7D5A79C3BC; RefreshToken=fc6b1bcc-1c00-4663-b6ef-441051fb2e57; sessionId=75bdbb27-cf85-4102-9ba7-0cc5a84f8fb4' \</p><p>--data-raw '{</p><p>    "direction": "ASC",</p><p>    "keyword": "",</p><p>    "pageNumber": 0,</p><p>    "pageSize": 16,</p><p>    "sort": "NAME"</p><p>}'</p> |

**Sample Response:**

**On success:**

`{`

`"success": true,`

`"data": {`

`"offset": 0,`

`"pageSize": 16,`

`"totalElements": 5,`

`"totalPages": 1,`

`"elements": [`

`{`

`"endDate": null,`

`"deprovNotification": false,`

`"enabled": true,`

`"tagLine": "Directory service developed by Microsoft",`

`"id": "617253cc2fb4b2125b237b75",`

`"name": "Active Directory",`

`"appUrl": "",`

`"icon": "iVBORw0KGgoAAAANSUhEUgAAALoAAAC6CAYAAAAZDlfxAAAACXBIWXMAAAsSAAALEgHS3X78AAAgAElEQVR4nO2dCXQU17nnv1tb.....truncated"`

`}`

`],`

`"pageNumber": 0,`

`"sort": {`

`"orders": [`

`{`

`"direction": "ASC",`

`"property": "NAME"`

`}`

`],`

`"sorted": true`

`}`

`},`

`"timestamp": "03-Mar-2022 05:41:09",`

`"message": null,`

`"errorCode": null`

`}`

### RESTful API – New Joiner List API <a href="#id-5ezhz9n77z32" id="id-5ezhz9n77z32"></a>

**Purpose:** This API is used to get list of selfservice dashboard new Joiner list of logged in users.

**URL: http://\<tenant\_url>/usersrvc/api/user/getSubOrdinates**

**Method: POST**

**Example Request: Need to pass filter as createdFrom and createdTo date time difference for seven day.**

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>curl --location --request POST 'http://api.cymmetri.in/usersrvc/api/user/getSubOrdinates' \</p><p>--header 'Content-Type: application/json' \</p><p>--header 'Tenant: gk17' \</p><p>--header 'UserId: 61e81227aa505f4393b93405' \</p><p>--data-raw '{</p><p>  "filter": {</p><p>    "createdFrom": "2022-01-04T10:26:56.030Z",</p><p>    "createdTo": "2022-03-04T10:26:56.030Z"</p><p>  },</p><p>  "keyword": "",</p><p>  "pageNumber": 0,</p><p>  "pageSize": 10,</p><p>  "sortDirection": "ASC",</p><p>  "sortOn": [</p><p>    "id"</p><p>  ]</p><p>}'</p> |

**Sample Response:**

**On success:**

`{`

`"success": true,`

`"data": {`

`"content": [`

`{`

`"login": "nilesh",`

`"displayName": "Nilesh Dhepe",`

`"userId": "61e947c37dce7c5e40134f1f",`

`"profilePic": null,`

`"qualitativeRisk": null,`

`"sodViolations": null`

`},`

`{`

`"login": "workflow.one",`

`"displayName": "Test Workflow",`

`"userId": "61ee658de3a8361263cab0d1",`

`"profilePic": null,`

`"qualitativeRisk": null,`

`"sodViolations": null`

`},`

`{`

`"login": "workflow.two",`

`"displayName": "Test Workflow",`

`"userId": "61f7b3b50d84c22f79e1debd",`

`"profilePic": null,`

`"qualitativeRisk": null,`

`"sodViolations": null`

`},`

`{`

`"login": "mrunal",`

`"displayName": "Mrunal Chaple",`

`"userId": "61f8cda757a8e27934066a91",`

`"profilePic": null,`

`"qualitativeRisk": null,`

`"sodViolations": null`

`},`

`{`

`"login": "manoj.b",`

`"displayName": "Manoj Barapatre",`

`"userId": "61f8d81883126a511188e2ae",`

`"profilePic": null,`

`"qualitativeRisk": null,`

`"sodViolations": null`

`},`

`{`

`"login": "man.ba",`

`"displayName": "Manoj Bara",`

`"userId": "61f9160ed9800d4dbbc1baed",`

`"profilePic": null,`

`"qualitativeRisk": null,`

`"sodViolations": null`

`}`

`],`

`"pageable": {`

`"sort": [`

`{`

`"direction": "ASC",`

`"property": "id",`

`"ignoreCase": false,`

`"nullHandling": "NATIVE",`

`"ascending": true,`

`"descending": false`

`}`

`],`

`"pageNumber": 0,`

`"pageSize": 10,`

`"offset": 0,`

`"paged": true,`

`"unpaged": false`

`},`

`"last": true,`

`"totalElements": 6,`

`"totalPages": 1,`

`"first": true,`

`"number": 0,`

`"sort": [`

`{`

`"direction": "ASC",`

`"property": "id",`

`"ignoreCase": false,`

`"nullHandling": "NATIVE",`

`"ascending": true,`

`"descending": false`

`}`

`],`

`"numberOfElements": 6,`

`"size": 10,`

`"empty": false`

`},`

`"timestamp": "04-Mar-2022 10:39:22",`

`"message": null,`

`"errorCode": null`

`}`

**On failure:**

**Response 1#**

`{`

`"success": true,`

`"data": null,`

`"timestamp": "04-Mar-2022 10:39:22",`

`"message": null,`

`"errorCode": null`

`}`

### RESTful API – On board API - Get App incomplete config <a href="#sgx2w09i9mzf" id="sgx2w09i9mzf"></a>

**Purpose:** This API is used to get count of onboard application config incomplete.

**URL: http://\<tenant\_url>/provsrvc/applicationTenant/getApplicationIncompleteConfig**

**Method: GET**

**Example Request:**

![](<../../.gitbook/assets/9 (2).png>)

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>curl --location --request GET 'http://api.cymmetri.in/provsrvc/applicationTenant/getApplicationIncompleteConfigCount' \</p><p>--header 'Tenant: gk17' \</p><p>--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJnazE3IiwiZGVsZWdhdGVlIjpudWxsLCJkZWxlZ2F0ZWVJZCI6bnVsbCwiZmlyc3RMb2dpbiI6ZmFsc2UsInJvbGVzIjpbIk9SR19BRE1JTiIsIlVTRVIiXSwidGVuYW50SWQiOiJnazE3IiwiZXhwIjoxNjQ2NjQ2NjQ0LCJ1c2VySWQiOiI2MWU4MTIyN2FhNTA1ZjQzOTNiOTM0MDUiLCJpYXQiOjE2NDY2NDA2NDR9.snwC7XVRWM5S-gCP53fXXObh9aROFtZDtfOXQCUDPps'</p> |

**Sample Response:**

**On success**`{`

`"success": true,`

`"data": 3,`

`"timestamp": "07-Mar-2022 08:11:48",`

`"message": null,`

`"errorCode": null`

`}`

**On failure:**

**Response 1#**

`{`

`"success": true,`

`"data": 0,`

`"timestamp": "04-Mar-2022 10:39:22",`

`"message": null,`

`"errorCode": null`

`}`

### RESTful API – On board API - Get appCount, adminCount, UserCount <a href="#kpcfihgkzux7" id="kpcfihgkzux7"></a>

**Purpose:** This API is used to get count of application, admin and user.

**URL: http://\<tenant\_url>/usersrvc/api/user/getOnboardCount**

**Method: GET**

**Example Request:**

![](<../../.gitbook/assets/10 (2).png>)

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>curl --location --request GET 'http://api.cymmetri.in/usersrvc/api/user/getOnboardCount' \</p><p>--header 'Content-Type: application/json' \</p><p>--header 'Tenant: n23' \</p><p>--header 'UserId: 6176c0b33c79f20dde6fd732' \</p><p>--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJnazE3IiwiZGVsZWdhdGVlIjpudWxsLCJkZWxlZ2F0ZWVJZCI6bnVsbCwiZmlyc3RMb2dpbiI6ZmFsc2UsInJvbGVzIjpbIk9SR19BRE1JTiIsIlVTRVIiXSwidGVuYW50SWQiOiJnazE3IiwiZXhwIjoxNjQ2NjQ2NjQ0LCJ1c2VySWQiOiI2MWU4MTIyN2FhNTA1ZjQzOTNiOTM0MDUiLCJpYXQiOjE2NDY2NDA2NDR9.snwC7XVRWM5S-gCP53fXXObh9aROFtZDtfOXQCUDPps'</p> |

**Sample Response:**

**On success:**

`{`

`"success": true,`

`"data": {`

`"appCount": 9,`

`"adminCount": 1,`

`"userCount": 25`

`},`

`"timestamp": "07-Mar-2022 08:11:27",`

`"message": null,`

`"errorCode": null`

`}`

**On failure:**

**Response 1#**

`{`

`"success": true,`

`"data": {`

`"appCount": 0,`

`"adminCount": 0,`

`"userCount": 0`

`},`

`"timestamp": "07-Mar-2022 08:11:27",`

`"message": null,`

`"errorCode": null`

`}`

### RESTful API – System KPIs API <a href="#id-5o4nd5scoliy" id="id-5o4nd5scoliy"></a>

**Purpose:** This API is used to get the count of application,role,rule,workflow,password policy,active user,total user and unlogged user.

**URL:https://\<tenant\_url>/usersrvc/api/user/getSystemKPICount**

**Method: GET**

**Example Request:**

![](<../../.gitbook/assets/11 (2).png>)

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <p>curl --location --request GET 'https://macos.cymmetri.in/usersrvc/api/user/getSystemKPICount' \</p><p>--header 'Accept: application/json' \</p><p>--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJhZG1pbiIsImRlbGVnYXRlZSI6bnVsbCwiZGVsZWdhdGVlSWQiOm51bGwsImZpcnN0TG9naW4iOmZhbHNlLCJyb2xlcyI6WyJPUkdfQURNSU4iLCJVU0VSIl0sInRlbmFudElkIjoibWFjb3MiLCJleHAiOjE2NDcwMDg1MjUsInVzZXJJZCI6IjYxN2Y4YmIxZDE5MDViNjcyYzQ3N2QzMiIsImlhdCI6MTY0NzAwMjUyNX0.JzhcbfcQXxZoCYH5Mi_HmRCHZf_FVIr3OYrewl7vkjc'</p><p> </p> |

**Sample Response:**

**On success:**

`{`

`"success": true,`

`"data": {`

`"appCount": 80,`

`"roleCount": 5,`

`"activeUserCount": 128,`

`"totalUserCount": 131,`

`"unloggedUserCount": 106,`

`"passwordPolicyCount": 2,`

`"workflowCount": 3,`

`"ruleCount": 6`

`},`

`"timestamp": "11-Mar-2022 12:42:30",`

`"message": null,`

`"errorCode": null`

`}`

**On failure:**

**Response 1#**

`{`

`"success": true,`

`"data": {`

`"appCount": 0,`

`"roleCount": 0,`

`"activeUserCount": 0,`

`"totalUserCount": 0,`

`"unloggedUserCount": 0,`

`"passwordPolicyCount": 0,`

`"workflowCount": 0,`

`"ruleCount": 0`

`},`

`"timestamp": "11-Mar-2022 12:42:30",`

`"message": null,`

`"errorCode": null`

`}`

### RESTful API – Request, Claims and My Request Count <a href="#id-676d2l2fu3z6" id="id-676d2l2fu3z6"></a>

**Purpose:** This API is used to get count of requests, claims and my requests.

**URL: https://\<tenant\_url>/workflowsrvc/api/workflowtaskassignment/user/request/claims/count**

**Method: GET**

**Example Request:**

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>curl --location --request GET 'https://gk40.cymmetri.in/workflowsrvc/api/workflowtaskassignment/user/request/claims/count' \</p><p>--header 'Tenant: gk40' \</p><p>--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJtcnUxOCIsImRlbGVnYXRlZSI6bnVsbCwiZGVsZWdhdGVlSWQiOm51bGwsImZpcnN0TG9naW4iOmZhbHNlLCJyb2xlcyI6WyJPUkdfQURNSU4iLCJVU0VSIl0sInRlbmFudElkIjoibXJ1MTgiLCJleHAiOjE2NDY2NzE2MTYsInVzZXJJZCI6IjYxNGI1Yjc1ODVmODU0NGYxY2RkOTcxNSIsImlhdCI6MTY0NjY2NTYxNn0.bViQdrikfQD1xdI6Waf_Sk6LOYQh-ilHVq4dMYfVt3E'</p><p> </p> |

**Sample Response:**

**On success:**

`{`

`"success": true,`

`"data": {`

`"requestCount": 12,`

`"clamisCount": 6,`

`"requestorCount": 0`

`},`

`"timestamp": "10-Mar-2022 07:07:48",`

`"message": null,`

`"errorCode": null`

`}`

**On failure:**

**Response 1#**

`{`

`"success": true,`

`"data": {`

`"requestCount": 0,`

`"clamisCount": 0,`

`"requestorCount": 0`

`},`

`"timestamp": "04-Mar-2022 10:39:22",`

`"message": null,`

`"errorCode": null`

`}`

### RESTful API – Applications assigned to user API search <a href="#jr7uplgxr4h7" id="jr7uplgxr4h7"></a>

**Purpose:** This API is used to search application assigned to user.

**URL: https://\<tenant\_url>/usersrvc/api/user/listApplications**

**Method: POST**

**Example Request:**

![](<../../.gitbook/assets/13 (1).png>)

|                                                                                                                                                                                                                                                                                                     |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>curl --location --request POST 'https://s3.cymmetri.in/usersrvc/api/user/listApplications' \</p><p>--data-raw '{</p><p>            "pageNumber": 0,</p><p>            "pageSize": 20,</p><p>            "userId": "61d7f610dd92d761faa278f2",</p><p>            "appName":"service"</p><p>}'</p> |

**Sample Response:**

**On success:**

`{`

`"success": true,`

`"data": {`

`"offset": 0,`

`"pageSize": 12,`

`"totalElements": 1,`

`"totalPages": 1,`

`"elements": [`

`{`

`"appId": "6226051994c38e414989eccd",`

`"appName": "ServiceNow",`

`"tagLine": "Workflow Automation Platform",`

`"status": "",`

`"appType": "GROUP",`

`"groupId": "61dea46ef515150ebe517b0d",`

`"endDate": null,`

`"provisionEnable": true,`

`"assignRoles": null`

`}`

`],`

`"pageNumber": 0,`

`"sort": null`

`},`

`"timestamp": "11-Mar-2022 01:06:33",`

`"message": null,`

`"errorCode": null`

`}`



### RESTful API – List of assigned & unassigned application <a href="#k6ecyz1ydmjh" id="k6ecyz1ydmjh"></a>

**Purpose:** This API is used to get assigned and unassigned application.

**URL: https://\<tenant\_url>/provsrvc/applicationTenant/applicationListByPage**

**Method: POST**

**Example Request:**

![](<../../.gitbook/assets/14 (1).png>)

|                                                                                                                                                                                                                                                                                                                                                                                                                   |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>curl --location --request POST 'https://s3.cymmetri.in/provsrvc/applicationTenant/applicationListByPage' \</p><p>--data-raw '{</p><p>            "displayName": "",</p><p>            "order": "DESC",</p><p>            "pageNo": 0,</p><p>            "size": 10,</p><p>            "sortBy": "displayName",</p><p>            "tag": "",</p><p>            "userId":"61d7f610dd92d761faa278f2"</p><p>}'</p> |

**Sample Response:**

**On success:**

`{`

`"success": true,`

`"data": {`

`"content": [`

`{`

`"id": "61dbfdf6b30690468b0d4a79",`

`"appName": "Google Workplace",`

`"icon": null,`

`"tagLine": "Integrated Collaboration & Productivity Apps from Google",`

`"status": "ACTIVE",`

`"provisionEnable": false,`

`"ssoEnable": true,`

`"assigned": true`

`},`

`{`

`"id": "61dd1da8db654e41881b5273",`

`"appName": "Active Directory",`

`"icon": null,`

`"tagLine": "Directory service developed by Microsoft",`

`"status": "ACTIVE",`

`"provisionEnable": true,`

`"ssoEnable": false,`

`"assigned": true`

`},`

`{`

`"id": "6225f81edd7111640e094f8d",`

`"appName": "Google Workplace5",`

`"icon": null,`

`"tagLine": "Integrated Collaboration & Productivity Apps from Google",`

`"status": "ACTIVE",`

`"provisionEnable": true,`

`"ssoEnable": false,`

`"assigned": true`

`}`

`],`

`"pageable": {`

`"sort": [`

`{`

`"direction": "DESC",`

`"property": "displayName",`

`"ignoreCase": false,`

`"nullHandling": "NATIVE",`

`"ascending": false,`

`"descending": true`

`}`

`],`

`"pageNumber": 0,`

`"pageSize": 10,`

`"offset": 0,`

`"paged": true,`

`"unpaged": false`

`},`

`"totalPages": 2,`

`"totalElements": 12,`

`"last": false,`

`"first": true,`

`"sort": [`

`{`

`"direction": "DESC",`

`"property": "displayName",`

`"ignoreCase": false,`

`"nullHandling": "NATIVE",`

`"ascending": false,`

`"descending": true`

`}`

`],`

`"numberOfElements": 10,`

`"size": 10,`

`"number": 0,`

`"empty": false`

`},`

`"timestamp": "11-Mar-2022 02:10:38",`

`"message": null,`

`"errorCode": null`

`}`



### RESTful API – Application Access expiring new API <a href="#id-1j2w8o8k8ip" id="id-1j2w8o8k8ip"></a>

**Purpose:** This API is used to get list of application of user with there expiry days

**URL: https://\<tenant\_url>/selfservice/api/selfservice/applicationswithexpiry**

**Method: POST**

**Example Request:**

![](<../../.gitbook/assets/15 (1).png>)

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| curl --location --request POST 'https://as100.cymmetri.in/selfservice/api/selfservice/applicationswithexpiry' \ --header 'Connection: keep-alive' \ --header 'Pragma: no-cache' \ --header 'Cache-Control: no-cache' \ --header 'sec-ch-ua: "Google Chrome";v="93", " Not;A Brand";v="99", "Chromium";v="93"' \ --header 'Accept: application/json' \ --header 'content-type: application/json' \ --header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJhZG1pbiIsImRlbGVnYXRlZSI6bnVsbCwiZGVsZWdhdGVlSWQiOm51bGwsImZpcnN0TG9naW4iOmZhbHNlLCJyb2xlcyI6WyJPUkdfQURNSU4iLCJVU0VSIl0sInRlbmFudElkIjoiYXMxMDAiLCJleHAiOjE2NDcwMDk4NzgsInVzZXJJZCI6IjYyMTRkYjdiZDY2MWE1NzM4NmE3MWYxMCIsImlhdCI6MTY0NzAwMzg3OH0.LKZci0Yqeoyn4RHUIyYBFq7O5ATeDuCerZ0QdJ243gY' \ --header 'sec-ch-ua-mobile: ?0' \ --header 'User-Agent: Mozilla/5.0 (X11; Linux x86\_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/93.0.4577.63 Safari/537.36' \ --header 'sec-ch-ua-platform: "Linux"' \ --header 'Origin: https://as100.cymmetri.in' \ --header 'Sec-Fetch-Site: same-origin' \ --header 'Sec-Fetch-Mode: cors' \ --header 'Sec-Fetch-Dest: empty' \ --header 'Referer: https://as100.cymmetri.in/' \ --header 'Accept-Language: en-GB,en-US;q=0.9,en;q=0.8' \ --header 'Cookie: deviceId=48ba110c-c93c-45ac-92dc-3c6e04e74473; app\_73e5c5f8-276b-47bb-a6a5-b6f82a779d79=e689a8da-faa7-46f5-9c7a-2800abdd206a; Correlation=C43A4277E7AB46178F0000BE4DD72F0C; RefreshToken=1ac7eea6-28a6-4bb8-997f-d7381a3dd7d1; sessionId=3417319f-789a-4849-8faa-bf180f4bec14; device=cf7bbf2a-161c-11ec-b3ec-39287c680726' \ --data-raw '{ "keyword": "", "pageNumber": 0, "pageSize": 10, "filter": {}, "sortDirection": "DESC", "sortOn": \[ "plannedStart" ] }' |

**Sample Response:**

**On success:**

`{`

`"success": true,`

`"data": {`

`"offset": 0,`

`"pageSize": 10,`

`"totalElements": 3,`

`"totalPages": 1,`

`"elements": [`

`{`

`"id": "62220c747dab08061e00ba7b",`

`"name": "Active Directory",`

`"icon": "iVBORw0KGgoAAAANSUhEUgAAALoAAAC6CAYAAAAZDlfxAAAACXBIWXMAAAsSAAALEgHS3X78AAAgAElEQVR4nO2dCXQU17nnv1tb71q7BUJIzW7Jxo5N6zlOsPD2COBlEsnbiZFf,`

`"period": 20,`

`"tagLine": "Directory service developed by Microsoft"`

`},`

`{`

`"id": "62260e904f6c552b8b489c20",`

`"name": "Google Workplace",`

`"icon": "iVBORw0KGgoAAAANSUhEUgAAALoAAAC6CAIAAACWbMCmAAAACXBIWXMAAAsSAAALEgHS3X78AAAgAElEQVR4nO2dd3wURf/Ht1xLcnfpvUB6uRRSKFKl9w6C+KgPj2B57D6gD/o8iOVBEaQIiCiIgoBKNSAgVXoPISG910u5S0+u7/xed3vZ27vsXW6T4A+fZ97/ZLM7uzs7+9mZ73xn5nsoAACBQOwDg+UEsR8oFwgLoFwgLIBygbAAygXCAigXCAugXCAsgHKBsADKBcICKBcIC6BcICyAcoGwAMoFwgIoFwgLoFwgLIBygbAAygXCAigXCAugXCAsgHKBsADKBcICKBcIC6BcICyAcoGwAMoFwgIoFwgLoFwgLIBygbAAygXCAigXCAugXCAsgHKBsADKBcICKBcIC6BcICyAcoGwAMoFwgIoFwgLoFwgLIBygbAAygXYQGUC4QFUC4QFkC5QFgA5QKxFwRB/g+Z9ki2AOTkrgAAAABJRU5ErkJggg==",`

`"period": 5,`

`"tagLine": "Integrated Collaboration & Productivity Apps from Google"`

`},`

`{`

`"id": "62260e994f6c552b8b489c28",`

`"name": "PowerShell",`

`"icon": "iVBORw0KGgoAAAANSUhEUgAAALoAAAC6CAYAAAAZDlfxAT/gAAAABJRU5ErkJggg==",`

`"period": 4,`

`"tagLine": "Command-line Shell from Microsoft"`

`}`

`],`

`"pageNumber": 0,`

`"sort": {`

`"orders": [`

`{`

`"direction": "DESC",`

`"property": "plannedStart"`

`}`

`],`

`"sorted": true`

`}`

`},`

`"timestamp": "11-Mar-2022 01:42:30",`

`"message": null,`

`"errorCode": null`

`}`



### RESTful API – Password Policy - maximum (optional)- minimum (required) password length <a href="#id-9u7bu81tyip1" id="id-9u7bu81tyip1"></a>

**Purpose:** This API is used to validate password against password policy

**URL: https://\<tenant\_url>/authsrvc/passwordPolicy/pub/validate**

**Method: POST**

**Example Request:**

![](<../../.gitbook/assets/16 (1).png>)

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>curl 'https://as100.cymmetri.in/authsrvc/passwordPolicy/pub/validate' \</p><p>  -H 'Connection: keep-alive' \</p><p>  -H 'Pragma: no-cache' \</p><p>  -H 'Cache-Control: no-cache' \</p><p>  -H 'sec-ch-ua: "Google Chrome";v="93", " Not;A Brand";v="99", "Chromium";v="93"' \</p><p>  -H 'content-type: application/json' \</p><p>  -H 'sec-ch-ua-mobile: ?0' \</p><p>  -H 'User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/93.0.4577.63 Safari/537.36' \</p><p>  -H 'tenant: as100' \</p><p>  -H 'sec-ch-ua-platform: "Linux"' \</p><p>  -H 'Accept: */*' \</p><p>  -H 'Origin: https://as100.cymmetri.in' \</p><p>  -H 'Sec-Fetch-Site: same-origin' \</p><p>  -H 'Sec-Fetch-Mode: cors' \</p><p>  -H 'Sec-Fetch-Dest: empty' \</p><p>  -H 'Referer: https://as100.cymmetri.in/' \</p><p>  -H 'Accept-Language: en-GB,en-US;q=0.9,en;q=0.8' \</p><p>  -H 'Cookie: deviceId=fa83c4b1-7c85-467d-9b46-ffbc70efad97; Correlation=9928D5133AED419CBC01591B56483953; app_73e5c5f8-276b-47bb-a6a5-b6f82a779d79=e689a8da-faa7-46f5-9c7a-2800abdd206a; device=cf7bbf2a-161c-11ec-b3ec-39287c680726' \</p><p>  --data-raw '{"password":"U2FsdGVkX191zbRQpSQz+rdxyAacEqD1G5Mx5wKtPV5ElwKZu7/TFHFLuCNH+v63G8k7sTFDa5gNYG9SQ+0ix4eZdTvLcJbELGm2yjUWjx2a6jH3JnP/USl2efCC9nDvufmqUhSbIPA0Nc1PZUqM+PPk+TpCFSoKtKwBPWeBa/LYjlYt11u++aTuVGsd/rOaWJxqINPRHIk6Ax89LfhM8+H6VKc4+ybfearoCJgHWCPE/X566hiYZJEKcMGe7u0OpUzGUMlyguBtfYlWlT7tcdP6x/rXlqs8vNTLk/HboYLv10UkB0ifsQ64c7fSQ/ofZKjQlqehpP4+SzIi4OiqRQikP9MOkKZWl9YJdGXZs+mUuzfEs9UGINMYBk1hSCq6xGb9mfE0vyFeVAyY/6oGgQ==","login":"totp","userId":"6214def0a251e06721ed8594"}' \</p><p>  --compressed</p> |

**Sample Response:**

**On success:**

`{"success":true,"data":null,"timestamp":"11-Mar-2022 01:40:38","message":null,"errorCode":null}`

**On failure:**

**Response 1#**

`{"success":false,"data":null,"timestamp":"11-Mar-2022 01:39:40","message":null,"errorCode":"AUTHSRVC.PASSWORD_COMPOSITION_RULE_VIOLATION"}`

### RESTful API – New Application count API (7 days) <a href="#id-1cpkdozkd9" id="id-1cpkdozkd9"></a>

**Purpose:** This API is used to get count of application

**URL: http://\<tenant\_url>/api/selfservice/newApplicationsCount**

**Method: GET**

**Example Request:**

![](<../../.gitbook/assets/17 (1).png>)

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <p>curl --location --request GET 'http://localhost:8080/api/selfservice/newApplicationsCount' \</p><p>--header 'Connection: keep-alive' \</p><p>--header 'Pragma: no-cache' \</p><p>--header 'Cache-Control: no-cache' \</p><p>--header 'sec-ch-ua: " Not A;Brand";v="99", "Chromium";v="99", "Google Chrome";v="99"' \</p><p>--header 'Accept: application/json' \</p><p>--header 'content-type: application/json' \</p><p>--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJhZG1pbiIsImRlbGVnYXRlZSI6bnVsbCwiZGVsZWdhdGVlSWQiOm51bGwsImZpcnN0TG9naW4iOmZhbHNlLCJyb2xlcyI6WyJPUkdfQURNSU4iLCJVU0VSIl0sInRlbmFudElkIjoiZ2s0MCIsImV4cCI6MTY0Njc0OTkzMiwidXNlcklkIjoiNjE3MDE1YTNjMDQ4MTc1NmI3OThhY2EyIiwiaWF0IjoxNjQ2NzQzOTMyfQ.puFKgrNoHZtRl6P4LxzFd9KQM_-EB-45DqqP4zywws8' \</p><p>--header 'sec-ch-ua-mobile: ?0' \</p><p>--header 'User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.51 Safari/537.36' \</p><p>--header 'sec-ch-ua-platform: "Linux"' \</p><p>--header 'Sec-Fetch-Site: same-origin' \</p><p>--header 'Sec-Fetch-Mode: cors' \</p><p>--header 'Sec-Fetch-Dest: empty' \</p><p>--header 'Referer: https://gk40.cymmetri.in/' \</p><p>--header 'Accept-Language: en-GB,en-US;q=0.9,en;q=0.8' \</p><p>--header 'Cookie: deviceId=6e4caedd-beaf-444c-9312-21b219bb3709; Correlation=B194B86832FB4683ABC43EA6077944E2; app_73e5c5f8-276b-47bb-a6a5-b6f82a779d79=e689a8da-faa7-46f5-9c7a-2800abdd206a; device=41b5bf50-9def-11ec-8665-953ee8af105c; Correlation=1B9449F921B043B9B513E99D253894CE; RefreshToken=b8ada8a1-d089-4a39-b3e1-72c04ce202fe; sessionId=130e95df-69a5-4462-a8b5-c04b53e97e64' \</p><p>--header 'Tenant: gk40' \</p><p>--header 'userId: 617015a3c0481756b798aca2'</p> |

**Sample Response:**

**On success:**

`{"success": true,"data": 1,"timestamp": "11-Mar-2022 02:13:39","message": null,"errorCode": null}`

### RESTful API – Campaigns/access review search by campaign name <a href="#pc702rjksp9m" id="pc702rjksp9m"></a>

**Purpose:** This API is used to get list of campaign

**URL: https://\<tenant\_url>/igsrvc/api/ig/campaign/execution/history/list-summary/reviewer**

**Method: POST**

**Example Request:**

![](<../../.gitbook/assets/18 (1).png>)

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>curl --location --request POST 'https://gk40.cymmetri.in/igsrvc/api/ig/campaign/execution/history/list-summary/reviewer' \</p><p>--header 'Connection: keep-alive' \</p><p>--header 'Pragma: no-cache' \</p><p>--header 'Cache-Control: no-cache' \</p><p>--header 'sec-ch-ua: " Not A;Brand";v="99", "Chromium";v="99", "Google Chrome";v="99"' \</p><p>--header 'Accept: application/json' \</p><p>--header 'content-type: application/json' \</p><p>--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJhZG1pbiIsImRlbGVnYXRlZSI6bnVsbCwiZGVsZWdhdGVlSWQiOm51bGwsImZpcnN0TG9naW4iOmZhbHNlLCJyb2xlcyI6WyJPUkdfQURNSU4iLCJVU0VSIl0sInRlbmFudElkIjoiZ2s0MCIsImV4cCI6MTY0NzAxNDY2NywidXNlcklkIjoiNjE3MDE1YTNjMDQ4MTc1NmI3OThhY2EyIiwiaWF0IjoxNjQ3MDA4NjY3fQ.jP2BgjiOVUcdxhImVvdwy18puEylWSSOVHnWA_2hhJU' \</p><p>--header 'sec-ch-ua-mobile: ?0' \</p><p>--header 'User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.51 Safari/537.36' \</p><p>--header 'sec-ch-ua-platform: "Linux"' \</p><p>--header 'Origin: https://gk40.cymmetri.in' \</p><p>--header 'Sec-Fetch-Site: same-origin' \</p><p>--header 'Sec-Fetch-Mode: cors' \</p><p>--header 'Sec-Fetch-Dest: empty' \</p><p>--header 'Referer: https://gk40.cymmetri.in/' \</p><p>--header 'Accept-Language: en-GB,en-US;q=0.9,en;q=0.8' \</p><p>--header 'Cookie: deviceId=6e4caedd-beaf-444c-9312-21b219bb3709; Correlation=B194B86832FB4683ABC43EA6077944E2; Correlation=C27A4466A21046309B58FD53AEF4A2C5; RefreshToken=4ec80313-bed3-44e5-9081-33eb9ba301f2; sessionId=32ceee83-781e-45d6-9c2c-2acc8741a944' \</p><p>--data-raw '{</p><p>    "filter": {</p><p>        "campaignName": "Campaign For"</p><p>    },</p><p>    "keyword": "",    </p><p>    "pageNumber": 0,</p><p>    "pageSize": 10,</p><p>    "sortDirection": "ASC",</p><p>    "sortOn": [</p><p>        "startDate"</p><p>    ]</p><p>}'</p> |

**Sample Response:**

**On success:**

`{`

`"data": {`

`"content": [`

`{`

`"executionId": "61a865c69c60c83eb2d2cf0e",`

`"name": "Campaign For Bug_w8z89q",`

`"description": "",`

`"campaignId": "61a8657c9c60c83eb2d2cf0c",`

`"revision": 1,`

`"iteration": 1,`

`"status": "COMPLETED",`

`"remarks": "",`

`"startMode": "MANUAL",`

`"startDate": "2021-12-02",`

`"endMode": "MANUAL",`

`"endDate": "2021-12-02",`

`"plannedEnd": "2021-12-05",`

`"totalAssignments": 41,`

`"pendingAssignments": 41,`

`"approvedAssignments": 0,`

`"rejectedAssignments": 0`

`},`

`{`

`"executionId": "6225c00ab21ac3024d5a1d91",`

`"name": "Campaign For Bug_w8z89q",`

`"description": "",`

`"campaignId": "61a8657c9c60c83eb2d2cf0c",`

`"revision": 1,`

`"iteration": 2,`

`"status": "COMPLETED",`

`"remarks": "",`

`"startMode": "MANUAL",`

`"startDate": "2022-03-07",`

`"endMode": "AUTO",`

`"endDate": "2022-03-10",`

`"plannedEnd": "2022-03-10",`

`"totalAssignments": 40,`

`"pendingAssignments": 40,`

`"approvedAssignments": 0,`

`"rejectedAssignments": 0`

`}`

`],`

`"pageable": {`

`"sort": [`

`{`

`"direction": "ASC",`

`"property": "startDate",`

`"ignoreCase": false,`

`"nullHandling": "NATIVE",`

`"ascending": true,`

`"descending": false`

`}`

`],`

`"pageNumber": 0,`

`"pageSize": 10,`

`"offset": 0,`

`"paged": true,`

`"unpaged": false`

`},`

`"totalPages": 1,`

`"totalElements": 2,`

`"last": true,`

`"first": true,`

`"sort": [`

`{`

`"direction": "ASC",`

`"property": "startDate",`

`"ignoreCase": false,`

`"nullHandling": "NATIVE",`

`"ascending": true,`

`"descending": false`

`}`

`],`

`"numberOfElements": 2,`

`"size": 10,`

`"number": 0,`

`"empty": false`

`},`

`"errorCode": null,`

`"message": null,`

`"success": true,`

`"timestamp": "11-Mar-2022 02:38:11"`

`}`

### API Response Codes <a href="#w1lohxsr0vh" id="w1lohxsr0vh"></a>

| **API**        | **Status**            | **Error Code** | **Message** |
| -------------- | --------------------- | -------------- | ----------- |
| **Create API** | 200                   | OK             |             |
| 500            | Internal Server Error |                |             |
| 401            | Unauthorized          |                |             |
| 403            | Forbidden             |                |             |
| 404            | Not Found             |                |             |
| **Update API** | 200                   | OK             |             |
| 500            | Internal Server Error |                |             |
| 401            | Unauthorized          |                |             |
| 403            | Forbidden             |                |             |
| 404            | Not Found             |                |             |
