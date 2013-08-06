---
layout: post
title: "Saviour WCF Routing service"
description: "WCF"
category: WCF
tags: [.NET, WCF, Routing]

---
{% include JB/setup %}
WCF in .NET had introduced Routing service.  In our past experience it has been saviour for business. Routing service does exactly what it sounds like "Routing".  Quintessentially  it routes message from one endpoint to other. I am not going to describe Routing service  in this blog because you can find more details on [MSDN] (http://msdn.microsoft.com/en-us/library/ee517421) website. I am going to describe two scenarios where we had used "Routing Service" in production environment.



## Scenario 1

Problem 1 : We had to work  under restriction where only one port was exposed  from application server to outside world and  presentation layer was expected  to reach any service on application server through that port. 

Solution : Routing service allows you to use content based routing to perform service aggregation . .NET relies on inbuilt message filter  or custom message filter to identify content in message and based on which it routes message to destination endpoints . 
Multiple message filter can be grouped into filter tables (derived from Filter table collection) and each entry in  filter table does mapping from message filter to destination endpoints.

## Scenario 2

Problem 2 : Among all the services we had installed on application server , one was getting blocked by too many requests. This was serious scalability issue.
 
Solution:  We defined custom message filter class which was routing message with same content to multiple instance of same service in round robin fashion. This is kind of poor man's load balancer but it has been extremely helpful  in achieving  scalability.

Next time it will be all about .NET code on this topic till then ...

