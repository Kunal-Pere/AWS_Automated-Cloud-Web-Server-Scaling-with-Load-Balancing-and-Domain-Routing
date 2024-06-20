### Now when we increase cpu utilization through stress command it goes above 80%, and our alarm will trigger and we receive notification through SNS service:

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/52ff25d3-2733-4c08-b503-6adcc5464ac9)


### Due to this our instance will scale-out that means as per our scaling policy, two more instance will add to our group as shown in below:

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/3063c745-8392-4e27-b10f-452c231962ac)

### Similiarly when the cpu utilization goes down below 60% then again alarm will trigger and we get notify through SNS service:

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/d2fe5074-d5f9-4163-a4aa-40fb9fd50130)


### Due to this our instance will scale-in that means as per our scaling policy, two instance will remove from our group:

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/7b7ca013-c330-4297-910a-fa4b59a17d38)

## SNS notification received when the cpu utilization goes above 80%:

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/95b87bac-a2b0-4b2d-8a3e-60d1f718febb)

## SNS notification received when the cpu utilization goes below 60%:

![image](https://github.com/Kunal-Pere/AWS_Automated-Cloud-Web-Server-Scaling-with-Load-Balancing-and-Domain-Routing/assets/157100045/174d549a-f5ba-4569-a1ea-7e6a9bf20263)
