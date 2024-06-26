### Now, we are creating Load Balancer to distribute traffic amaong the instances
### Follow the below given steps to create Load Balancer

### Step 1 :-
### Go to EC2 ==> Load Balancers ==> Create Load Balancer

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/e46b2459-1f15-4840-96da-25ced998e4d6)

 
### Step 2 :-
### Select the required Load Balancer type based on our use cases. Here we selected Application Load Balancer.

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/30ba49b2-63df-4947-8c1b-5fa91b6670a4)

 
### Step 3 :-

### In Basic Configuration, give the appropriate name to your Load balancer

### Select Internet-facing Scheme as our traffic is coming from internet.

### Select the IP address type as IPv4 as our subnet using IPv4 addresses

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/e0677cab-7a74-4487-ba9b-582933223e09)

 
### Step 4 :-

### In Network mapping section, select the VPC, Subnets and Availability Zones as shown below

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/05837bb7-7704-495c-82f8-71fb58fc2e04)

 
### Step 5 :-

### Select the Security Group

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/fb93559d-8492-401f-a661-49ddc2d0688b)

 
### Step 6 :-
### In Listener and Routing section, select appropriate protocol, port number and our Target Group on which we are sending traffic

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/eaeda451-64c4-4876-adba-f6827ecb6c67)

 
### Step 7 :-
### Click on Create Load Balancer option

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/19bed13a-15db-452a-a769-6872fac80608)

 
### Our Load Balancer is got created now and ready to serve traffic using the DNS name
 
 ![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/e9661aa9-e9e4-40db-9100-2b5bc34f175b)

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/0797489f-beb0-4d00-8976-7d0473708a04)


### Copy and paste this DNS Name on browser and you will see the apache or nginx page at first.

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/28c1f31f-6e94-49e6-bd05-1d6faf4c53d3)

 
### Refresh the page and you can see that the load balancer now distributed the traffic to the nginx page as shown below.

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/07192d9a-00b9-4c64-9886-798f91d3d091)

 
### That means, we set up Load Balancer correctly as it is sending traffic to our servers using Round-Robin method.

