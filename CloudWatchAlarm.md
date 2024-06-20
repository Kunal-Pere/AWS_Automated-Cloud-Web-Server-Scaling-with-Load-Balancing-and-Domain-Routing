Now, we will create CloudWatch Alarms with SNS Topic so we can use them in our Scaling Policy
Let's create below CloudWatch Alarms to trigger the Auto Scaling event

When CPU Utilization of apache-server is >=80 %
When CPU Utilization of apache-server is <=60 %
When CPU Utilization of nginx-server is >=80 %
When CPU Utilization of nginx-server is <=60 %
Steps are as follows
Go to CloudWatch ==> All Alarms ==> Create Alarm

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/9582a55f-a0a8-41e3-ae7d-8e058319cf00)

First let's create alarm to trigger auto scaling policy when CPU Utilization of apache-server is equal to or above 80 %

Specify metric and conditions
Click on Select metric option

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/b64bf228-dd60-46b2-93a3-296117e960ba)

Go to EC2 ==> Auto scaling Group ==> Select apache-ASG CPU Utilization

Click on Select Metric

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/9ec36d9f-82ec-4223-911c-111bdcf5517a)

Select metric Satistic as maximum and Period as 1 minute

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/743bc941-566e-445e-b7d8-d2015291e5a9)

We will select conditions as per our requirements

i.e. If the maximum CPU Utilization within given Period of 1 minute is equal to or above (Greater / Equal >= threshold) our threshold value of 80, then trigger the alarm.

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/a7120f2f-16bf-4bad-a6dc-ea361c7e0c9a)

Configure Actions
Select In Alarm state (when alarm trigger, alarm will go in In Alarm state)

Create a new SNS topic as shown below and give email id on which you will receive notifications

Click on Create Topic


