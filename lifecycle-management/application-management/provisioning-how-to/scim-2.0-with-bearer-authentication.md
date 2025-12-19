# SCIM 2.0 with Bearer Authentication

1.  Any application which supports SCIM v2.0 with bearer token is workable for application.<br>

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003459811/original/PSROuSBIchNyli__tGejfJE4XLTOK7bpxg.png?1649374849" alt=""><figcaption></figcaption></figure>

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003459814/original/eWZHLXTTUNIfL7I_RDyfB5qTghrAU-7sXA.png?1649374869" alt=""><figcaption></figcaption></figure>

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003459840/original/uHqKKvrJ6ZMP6tV-TDINn8ssl0F0fwASlQ.png?1649374883" alt=""><figcaption></figcaption></figure>

    <figure><img src="https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003459860/original/xXORmTT9bkY_ZlS76tn54MxZ1VI-6mGAPw.png?1649374894" alt=""><figcaption></figcaption></figure>
2. Following are configuration which is used for SCIM with bearer.
   1. Base address - It is the endpoint of the target system which supports SCIM v2 API’s.
   2. Username - Username to authenticate SCIM API endpoint.
   3. Password - Password to authenticate SCIM API endpoint.
   4. Security Token - It is a token which is used to authenticate.
   5. Grant Type - It is grant type which is used to grant access for API’s.
   6. Client Id - client id for authentication
   7. Client Secret - client secret for authentication
   8. Authentication type - It is Fixed Bearer compulsory.
   9. Update method - Patch or Put method.
   10. Accept - Http header which accepts (application/json etc).
   11. Content Type - Http header which accepts (application/json etc).
   12. Access Token Base Address - base address for access token
   13. Access Token Node Id - node id for access token
   14. Access Token Content Type - content type for access token.
