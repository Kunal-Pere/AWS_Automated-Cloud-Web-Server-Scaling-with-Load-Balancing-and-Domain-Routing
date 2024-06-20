### After creating Launch Templates (apache-LT and nginx-LT), let's create two Auto Scaling Groups having apache-LT in one and nginx-LT in another.

### Follow the below steps to create Auto Scaling Groups:

#### Go to EC2 ==> Auto Scaling ==> Create Auto Scaling Group

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/4d0a1ca1-edca-4712-b1b0-e67f30de858c)

### Step 1 :- Choose launch template

#### Give the appropriate name to your Auto Scaling Group
#### Select the Lauch template and click on Next button

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/93a80380-5106-4b29-b0fe-1cfd79bc2338)

### Step 2 :- Choose instance launch options

  Select VPC, Availability Zones and subnets and click on Next.

### Step 3 :- Configure advanced options

  Click on the option "Attach to an existing Load Balancer"
  Then choose option "Choose from your load balancer target groups"
  Select the Target Group as shown below

