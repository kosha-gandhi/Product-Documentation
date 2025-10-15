# REST Connector Provisioning

Integration REST Application

1. The REST connector is designed to manage provisioning by relying on RESTful service.
2. For REST applications we need target applications which support REST API’s.
3. Following configuration is tested for felicity application.
4. We need REST API’s to integrate with cymmetri.
5. Following are the cymmetri configuration which need to configure in user configuration in cymmetri.
6. It is Basic REST configuration which need to configure in application.

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003459764/original/Nf5IkJXLHPE7R89McTxYcClKHRbMWNPV9Q.png?1649374607)

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003459774/original/hC6w0yXpo8UlEVteZOr2ADnJvMm2pN-ATg.png?1649374616)

![](https://s3-ap-south-1.amazonaws.com/ind-cdn.freshdesk.com/data/helpdesk/attachments/production/84003459777/original/xoGRkkiJ9_Q2dtOLuCKXCKJ7ni3PBL-FAg.png?1649374628)

1. We need to provide Groovy code to run create user, update user, delete user and also recon pull and push (for recon pull we need to add sync script and for recon push we need to add search script)
2. For sample script please validate following link

[https://drive.google.com/drive/folders/1Vs8y1ZHXV3AjqsPkQSnwUoVppL-yc8Vl?usp=sharing](https://drive.google.com/drive/folders/1Vs8y1ZHXV3AjqsPkQSnwUoVppL-yc8Vl?usp=sharing)&#x20;



Note: Please Configure script step by step

1. Configure test script at initial step and then test configuration for provided script (If configure successfully then only go for step b).
2. Configure create script and test configuration (If successfully configured then only go for step c).
3. Configure update script and test configuration (If successfully configured then only go for step d).
4. Configure delete script and test configuration (If successfully configured then only go for step e).
5. Configure sync(pull) script and test configuration (If successfully configured then only go for step f).
6. Configure search(push) script and test configuration (If successfully configured then only go to the next step).
