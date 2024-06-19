## First we need to create two instance.

*  One instance is for apache web-server.
*  One instance is for NGINX server.
-----------------------------------------------------

## Steps to create EC2 Instance:

* Login to AWS account
* Search EC2 on search-bar
* Click on launch-instance
* Give suitable name to your instance
* Select AMI as "Ubuntu 22.04 LTS"
* Select Instance type as "t2.micro"
* Select key pair (its recommonded)
* Select security group
* select EBS volume
* And last click on launch instance.

  create another instance with same configuration and give name as per below:
  

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/138c5b82-6b2c-453f-97ce-725556a12588)


-------------------------------------------------------

## Install apache web-server on one instance and NGINX is on another using below command.

    sudo apt update
  
    sudo apt install apache2 -y

    sudo apt update
  
    sudo apt install nginx -y


## Once done with instance creation and configuration lets create image of this instances. which will help us in auto-scaling to select the specific AMI in launch template.

Follow below steps for AMI creation:-

  ![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/68f46296-69df-41d0-99dc-5fbc0a78494a)
  

## Create two AMI from instance as we have Apache web server and NGINX web server respectively.


  ![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/5cba1e07-feaa-4447-a2fe-032999cf8f81)

  





