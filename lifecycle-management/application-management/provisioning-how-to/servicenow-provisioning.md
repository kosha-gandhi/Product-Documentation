# ServiceNow Provisioning

To configure ServiceNow Application with cymmetri we need to configure Active Directory application. Please follow the steps provided below.

1. Get ServiceNow application from Cymmetri Master apps.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXd6H1owyR6hzreJi9Rs56k9WjLGGUYQuEXmc178mxEmG100mDY4aYOIhdJW4842Xx-UckgyGlqURGYf1-zj3_yFNSdU3FFKXvfGqRlQE-zGdWqJ-Yx5U3MI2TbupVRr_rljRYUn2x2vNIEXLLvevc0cGE0?key=lUE454jiBC3DhVb2sxeZBA" alt=""><figcaption></figcaption></figure>

2. After Getting application from cymmetri master activate provisioning of selected application i.e Service Now.
3. After successfully activating provisioning, setup server configuration.

&#x20;           Note: Basic configuration is already provided in cymmetri master application. If the       connid server is configured externally then configure server config as per requirement.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXfYFVQXrqNgMzyIMVXMPwDg2qOrnxuKZlvJGgMXH5AmSo8pk_vfq48POEcLWGiUNYdTRPbVSGkOM9vxUH2N99Im9rGiV_OxLdntvFZ2waO1s6oGJ8Yi5w67MX4ggHv0wRYSsG_LJrTgEQ6_oqJO1Wzf7M9a?key=lUE454jiBC3DhVb2sxeZBA" alt=""><figcaption></figcaption></figure>

4. Successfully configuring server configuration, next step is to configure User Configuration. This is the most important step to connect and perform operations with Service Now.

For User configuration we need User config base address,User config username and User config base password  for all these credentials first we need to create account in Service Now which is a target application

Create account by clicking on below link

[https://developer.servicenow.com/](https://developer.servicenow.com/) and sign in to the account.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXevpaTDPHik0D8lsK8dkugpfGQ62r2KAqsz43OpSyUCZ1ljMJJ_INdPaQ6nRQZHSfqBCbauwNha2WUVGyFFr4zrtb1MYV8xbrtQGBqhwbuFpnf9gIpJ9m_zIs3BYYORFM_MUZlmBX2VWGvuXTaXNq4P5JJq?key=lUE454jiBC3DhVb2sxeZBA" alt=""><figcaption></figcaption></figure>

After clicking continue we have to enter a verification code which we will get from the entered email address.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdQ-z_kOgARuIQrPoDmYAJkotPdUTAQtch0xG096q3sEYJghhMdhBCXW1wuxoaABSQ9k4SPtslqe6vc9BSfzbcM9ZPSlwn2QGgqGMIg4xEMDe5JZG5H5QUb8DyJ8RuOEpUuQEzWrYi_EIOy9jkFI1__UT0?key=lUE454jiBC3DhVb2sxeZBA" alt=""><figcaption></figcaption></figure>

Now we can go to Service Now account and click on My Profile and setting&#x20;

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdXOYehKNRrTe0ziB-67TsngRx7nJizL_1Og-5SV5F3miE3ZCyYeCYqeQmmxNpEWHOYp8wWNvWkZS0tiJHSCklFIBvMtmtSd6_Ziw-m9W9x5stJZYCmWqBZUogXoDDXVP9-j9Gl9wf3CBVnm4kYHn3Digs?key=lUE454jiBC3DhVb2sxeZBA" alt=""><figcaption></figcaption></figure>

it again asking for verification code.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXczDqdDTLev0osExrtRwiQ_PuIuvtvuTsNXT3yPuZGWUbooz1FEsS50xg7VlHLIK50eY-Y6yjrI23Lha5mn6-eaY8fDoYvb-fIS8KRjYpbebglqvCHwa0TIU05gzRmXtwka5AurRUsTbT20jwR5EDhdzdON?key=lUE454jiBC3DhVb2sxeZBA" alt=""><figcaption></figcaption></figure>

Enter the verification code and verify the account.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdyS6Wgs-043lf0qGndcrZYHsFJqr9aueD6ebumhrtyNMArFoU4hPufHlNoGNgQDKfUU2opYXipqTfu6Q0RqdwF4CqSlkSVhlv5M_wmtpjHHa5qYDsx784dn6QIn0BIWPuRqDYODbmaSy4NTHBWk6MztLQ?key=lUE454jiBC3DhVb2sxeZBA" alt=""><figcaption></figcaption></figure>

Then click on Developer Program option

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXfuMVW2PaI8EwUdXGi12Nh97ZXF64Wm81QBGws8o4O3jAE8pd4VxfdhWJKGpThZST5zhm35oaObyus3ra1QUP9qHodpSSzkXMFvjriBlITW-KRiO20rEz_Cekg8aXCGZYqBL0bjG-pLQ27myc7rDjNgW9gX?key=lUE454jiBC3DhVb2sxeZBA" alt=""><figcaption></figcaption></figure>

Now check the job responsibilities for admin account  as shown in the screenshot

Now click on “Start building” tab for setting up an instance.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXf7tVTRTEdh70AA4ye19UZ6ZANf-HjUJnL8AYQSb4RPKaoZXSWEk57KARwQxfcAzAezOOkNfFAskomnGa4QkMM-rvlHhtIHn5yJ18beQowHttWEeaHqa1vjzbSBig-3rkN6QbnIss0drwiST_cJvUh3E6UF?key=lUE454jiBC3DhVb2sxeZBA" alt=""><figcaption></figcaption></figure>

After setting up an instance we will get credentials for configuring the service now.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXcWxISe6zdHmLe6DFJxHDPmCgh8_CZsWChNWIyrsn9NPZUrukD0MGfoGspYVEwK-YVWwVAtMVqhUhVO2WqWyVQw7RQLNMEsxSwEBJ5YQrasKbmTnmcem-Na6-olfSEVruva2c0kj6UMkreWMo1-FMxV_xY?key=lUE454jiBC3DhVb2sxeZBA" alt=""><figcaption></figcaption></figure>

Add these credentials to the user configuration and save and test the configuration.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXepgJyjkTiX_96PpHRroK2ITnojkoJVhiRyfzzTkvOfI5JgIFdDj2Jr3YTZqsgoZX1atjpj-HJsXLVB2xHEVQ2XDo958yBzOU5jXirutOuW7kG0RTmSxTT7veaQwyYwsBgNorGfVdWjMhuuy6CySPXZYFY?key=lUE454jiBC3DhVb2sxeZBA" alt=""><figcaption></figcaption></figure>

Now we have to add the policyAttribute which is not available. Go to policyAttribute and click on Add New button.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXc4Q5a4k8dC3AKIgtwbLcvmT7tS8-pPtw3X38z_ag8DsXsT2fSRPy3L6175NCMcphTUgz1r3VxnvGMtQ5h4RZbTbIB7CSZqr_Mjzok1kTdcOnGdLr3vKY74Dtn1KWkhKaRBEg8OKHmJ54Ez-S49oz7eCyzD?key=lUE454jiBC3DhVb2sxeZBA" alt=""><figcaption></figcaption></figure>

After clicking on the new button we have to add policyAttribute.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXcQFO3Wb1VIJ70My6iniPw8WiO80Z4xVkmEgS11MIN7ssl6hkrTX7WW0u9FI898j1JWUVWZJTxWx86fGkFgfpDiViq_W-Dy6zTvz2wMvNN-9RxxUZA6f0i4D2KF3hSB4kOgo7Wce-qUe_GO_5TGX1H97Iri?key=lUE454jiBC3DhVb2sxeZBA" alt=""><figcaption></figcaption></figure>

Now we also need to map the policyAttribute name and description and save it.

After completing policyAttribute we need to map these attributes with the cymmetri fields.

Go to policyMap and for user policyMap click on AddCymmetriField.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXctACQDtieW7R_XWgIDdm_N-On_rN3b9CyBN2ySGr2J6ioWkcn7dPHRnLEPQy6ZdE-PzrE8BmdDpuDZWRnH2g2ZPe9e3h_dZzT67x5IbecTxzmJpg3bFZMRFBnlUVwLrOqeIwu8h2rb9CkTcf-9ojpceYmm?key=lUE454jiBC3DhVb2sxeZBA" alt=""><figcaption></figcaption></figure>

After clicking Add Cymmetri Field, window will open&#x20;

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdYELWKc_cBvw90-s_VXcfjK1xfKcFhAMI2dlaX-yxJ1F7DJWkVKWXv4gzVsK-NDl_0I6MoQTNm27pZ8WZa_Zqw-j0GEyE6h14RSZUbLH9kEUcwzPVQoYVk9w5-u3Ki9eehhDEf8O_2lgrqmDyFF9jFtkw?key=lUE454jiBC3DhVb2sxeZBA" alt=""><figcaption></figcaption></figure>

Click application field and select field which we want to map with cymmetri field (Select Cymmetri Field) and check create Only and Update Only tab and if we want to make any field as unique field then check Is User Principal checkbox and save it.

&#x20;           Map remaining field as above just remember which field is unique(is user Principal        marked checked).

After all configuration with these above steps now we are able to assign Service Now  Application to the user. To check whether a user created or not to the target application we need to go to Service Now account click on All and search for Users&#x20;

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXco0_91le8O0_whYTw7DYKT_HnuxR4BBB51ftL1GJ1yDjFgOOOXU0b6__2ONfBo3_vaS6WOyOH1V6ntCetjaiLWam2vycquYW6ylmvAnp1nmrHeAACXxz_p9cD4jCDodW33RfTLM5oOUk_hK3qaLke5e75a?key=lUE454jiBC3DhVb2sxeZBA" alt=""><figcaption></figcaption></figure>

Here we will get all the user list.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXcLnIdcCiRKp3XeY2XE5gQk4bEn_VWF9DSo3k4lEaTmw4yreth-za-Kr18zxbGmcwQPlqXsR9pgwah6G9EGhQSWvJBMsysO6gn1TIR9y24gW4kQ-o4tkl_09LnBKoG5PA9codE_dCpWewmA0ginLOURSb1G?key=lUE454jiBC3DhVb2sxeZBA" alt=""><figcaption></figcaption></figure>
