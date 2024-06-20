## After creating Launch Templates (apache-LT and nginx-LT), let's create two Auto Scaling Groups having apache-LT in one and nginx-LT in another.

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

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/b2c217e7-ebc4-4254-8229-ac81e8035eaa)


### Step 4 :- Configure group size and scaling

  Set Desired Capacity = 2 Min desired capacity = 1 Max desired capacity = 4

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/424cef5b-0372-4844-9976-140783cccaf7)

### Step 5 :- Add notifications (optional)

This section is optional so we don't need to add anything here.

### Step 6 :- Add tags (optional)

If required, we can add tags here but for now we are not adding anything here.

### Step 7 :- Review

Review the all selections and click on "Create Auto Scaling Group"

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/42c6f395-8580-46da-aa38-d298970a47c8)

We just created nginx-ASG. Similarly follow the above steps and create apache-ASG having apache-LT Launch Template
Now, both the Auto Scaling Groups are created as shown below

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/4a70d497-8f38-4a98-b473-ebb1488e211a)

After creation, you will see the instances are created exactly equal to the desired capacity (2) given in each Auto Scaling Group.
We can see 4 instances got created (2 of apache-server and 2 of nginx-server)

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/da519d07-dbf5-4317-bce2-21983841499d)

Now we need to add the Auto Scaling Policies in apache-ASG and nginx-ASG so that it will add or remove the instances as per the CPU Utilization

For that follow the below steps
Let's create scale-in policy in nginx-ASG for removing instances when CPU utilization is equal to or below 60 %

Open nginx-ASG ==> Automatic Scaling ==> Create Dynamic Scaling Policy

Select Policy type as Simple Scaling

Give the name to your policy

Select CloudWatch Alarm from drop down menu (Nginx_CPU_Utilization_<=60%)

Select the action which should happen after triggering selected alarm and click on Create
 
![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/7f92849b-2c0f-4e38-84d8-122091712a53)


Follow the above procedure and create the scaling policy for adding instances when CPU utilization is equal to or above 80 %

We have created both Scale-in and Scale-out policies as shown below.

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/962c2140-9911-4d04-9316-0b044443a8fe)


### Similarly create the scale in and scale out policies for apache-ASG

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/8433c9c2-0cff-4266-9e85-5a1a76214b2d)

