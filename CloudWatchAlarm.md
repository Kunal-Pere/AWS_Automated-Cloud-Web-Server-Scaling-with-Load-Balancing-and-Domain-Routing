## Now, we will create CloudWatch Alarms with SNS Topic so we can use them in our Scaling Policy Let's create below CloudWatch Alarms to trigger the Auto Scaling event

* When CPU Utilization of apache-server is >=80 %

* When CPU Utilization of apache-server is <=60 %

* When CPU Utilization of nginx-server is >=80 %

* When CPU Utilization of nginx-server is <=60 %
  
#### Steps are as follows

* Go to CloudWatch ==> All Alarms ==> Create Alarm

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/9582a55f-a0a8-41e3-ae7d-8e058319cf00)

### First let's create alarm to trigger auto scaling policy when CPU Utilization of apache-server is equal to or above 80 %

* Specify metric and conditions
* Click on Select metric option

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/b64bf228-dd60-46b2-93a3-296117e960ba)

* Go to EC2 ==> Auto scaling Group ==> Select apache-ASG CPU Utilization

* Click on Select Metric

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/9ec36d9f-82ec-4223-911c-111bdcf5517a)

* Select metric Satistic as maximum and Period as 1 minute

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/743bc941-566e-445e-b7d8-d2015291e5a9)

* We will select conditions as per our requirements

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/e42227da-4997-4b97-b195-c25695bbe012)

Preview and click on Create Alarm

Follow the same steps given above to create Alarms for below conditions :
To trigger auto scaling policy when CPU Utilization of apache-server is equal to or below 60 % (Create SNS topic in this for CloudWatch_Alarms_below_60%)

To trigger auto scaling policy when CPU Utilization of nginx-server goes above or equal to 80 % (use "CloudWatch_Alarms_above_80" SNS topic)

To trigger auto scaling policy when CPU Utilization of nginx-server is equal to or below 60 % (use "CloudWatch_Alarms_below_60" SNS topic)

Our alarms are now created
* i.e. If the maximum CPU Utilization within given Period of 1 minute is equal to or above (Greater / Equal >= threshold) our threshold 
  value of 80, then trigger the alarm.

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/a7120f2f-16bf-4bad-a6dc-ea361c7e0c9a)

* Configure Actions
  
* Select In Alarm state (when alarm trigger, alarm will go in In Alarm state)

* Create a new SNS topic as shown below and give email id on which you will receive notifications

* Click on Create Topic

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/7306ac75-3325-42df-b94c-5d25421c13d8)


* Give alarm name and click on next

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/4bd58443-f41c-446b-9e39-69f4ddcd1823)


Preview and click on Create Alarm

Follow the same steps given above to create Alarms for below conditions :
To trigger auto scaling policy when CPU Utilization of apache-server is equal to or below 60 % (Create SNS topic in this for CloudWatch_Alarms_below_60%)

To trigger auto scaling policy when CPU Utilization of nginx-server goes above or equal to 80 % (use "CloudWatch_Alarms_above_80" SNS topic)

To trigger auto scaling policy when CPU Utilization of nginx-server is equal to or below 60 % (use "CloudWatch_Alarms_below_60" SNS topic)

Our alarms are now created

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/5d3b03b1-8f09-43d6-a941-94cf5cc7a44c)

We can create a dashboard so that we can see the CPU Utilization of both the servers on the graph

Follow below steps to create Custom Dashboard

Go to CloudWatch ==> Dashboards ==> Create Dashboard

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/199ce0e3-8374-493d-9562-b9d2216d8f38)

Give a meaningful name to your dashboard.

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/368e1bd7-58a0-4850-acf3-8299379abf66)

Select Data Source as CloudWatch, Data Type as Metrics and click on Next

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/d2cb9f6e-13e3-4f07-b21d-0cff29e00e0f)


In Metrics, go to EC2 ==> By Auto Scaling Group and search for CPUUtilization in search box.

You will see apache-ASG and nginx-ASG. Select both and click on Create Widget.

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/f26cd0fa-af33-4d3c-9afa-33535a8a0335)


Make the changes on the next screen as you want and click on Save button.

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/baf7e46e-40fa-463e-a441-1111beeaa455)

We can see in Amazon SNS service (Simple Notification Service), that our SNS Topics are now created.

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/42239082-0d70-41f9-96ca-9f35bc4e0fd2)

You will receive the AWS Notifications over email similar to shown below for confirmation of subscription.

Click on Confirm Subscription to receive the notifications when your alarm triggers.

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/4c8d1eb9-536f-4324-b503-2ebf16411ee3)


Now you can see subscription status is "Confirmed" now


