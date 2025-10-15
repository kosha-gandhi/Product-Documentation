# Github Provisioning

Github Enterprise provides provisioning using SCIM 2.0

\
Pre-requisites

1. Create an account in Github (Enterprise).
2. Enable SAML for the Github tenant to be used with Cymmetri.



Step 1. Configure SSO in Cymmetri

Note the application URL received from the Git SAML configuration

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003459962/original/-OT8GcFjzvhANoty7uAdkgUvAaZClc9USw.png?1649375220)

Continue the configuration by logging into Cymmetri using at least Application Administrator role

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003460010/original/OREyuWixbNL1IPy3XMxlbmK514GdGs3pvg.png?1649375263)

Note: Public certificate gets from SSO metadata(cymmetri) and format it using following

[https://www.samltool.com/format\_x509cert.php](https://www.samltool.com/format_x509cert.php)&#x20;

Note: Make sure when you test SAML then in cymmetri login with github admin users loginid which is added in cymmetri.

Configure Profile Mapping

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003460027/original/RKhO4SRvbHtVGrZQ75e0RwBRfC8o5p1Ftw.png?1649375364)

Create User in Cymmetri and make sure login id of Cymmetri is same as gitHub Admin user login id.&#x20;

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003460028/original/OKsFrebzBHV2wA7zGF_0t2S6G0iRgYq2NA.png?1649375380)

Test SSO with the Cymmetri user.

1. Configure **SCIM v2.0 (Github)** application from master (cymmetri).
2. Basic provisioning policy attribute and policy map already aaded in default schema.
3. Github Application is run using Fixed Bearer token.
4. To get Fixed bearer token following steps used.

Step 1: Go to user settings in github

Step 2: Go to developer settings

Step 3: Go to personal access token and generate new token

Step4: Click on Configure SSO

Step 5: Click on Authorize

1. Use following cymmetri provision configuration and change according to github account.
2. Fixed Bearer Value copy from personal access token
3. Click on save
4. Click on Test Configuration with success message.
5. Check Policy map
6. Disable default for the respective attribute
