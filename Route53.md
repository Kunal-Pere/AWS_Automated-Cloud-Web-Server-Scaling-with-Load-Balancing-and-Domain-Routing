## Now lets use aws domain service Route 53. In the AWS Management Console, locate and click on "Route 53" under the "Networking & Content Delivery" section.  

* #### Create a Hosted Zone.

* #### Click on "Create Hosted Zone".

  ![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/9fc6d983-e03b-43e6-a274-aa6056668004)

  
*  #### Give the suitable domain name, discription and type as a private hosted zone.

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/796c11de-824f-4709-b553-749fbc948de6)


*  #### Now select your AWS region and VPC ID and click on create hosted zone.


![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/c3fa85c3-2d4c-4d6b-82fe-c5323116cead)


*  #### Once we done with the hosted zone, select it and inside that create a record and follow the below steps.

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/1c8eb010-fb0d-461f-b176-8848a98af27f)



* ### Now copy the record name as showing below and check it on instance that our traffic is going on both the server or not. Because we have used alias as loadbalncer and we have provided DNS of loadbalancer in alias as shown in above screenshot.

  * ### use below command to check that we can access both server or not.
 
        curl my_project.apache_nginx

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/75b8064e-d5ea-4d02-ac79-649f56f370f7)

