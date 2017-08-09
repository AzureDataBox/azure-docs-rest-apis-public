---
title: .... REST API | Microsoft Docs
author: gwallace
ms.author: gwallace
ms.date: 
ms.topic: reference
ms.service: Azure
ms.devlang: rest-api
service_description: To be added
---

# Load Balancer REST API

Load balancer allows fine-grained configuration of how incoming traffic is distributed across VM instances hosted in Microsoft Azure. A load balancer has two main parts: a frontend and a backend configuration. The frontend configuration describes the exposed IP address of the load balancer. The frontend IP address of a load balancer can be a public or private IP address. The backend configuration of a load balancer describes how the traffic is distributed across VM instances and how health of a particular VM instance is determined.  

| Operation | REST Verb | Description | 
|---------|---------|-----------|
| [Create or update a load balancer](~/docs-ref-autogen/load-balancer/loadbalancers.json#LoadBalancers_CreateOrUpdate)   |  PUT | Creates or updates a Load balancer. | 
| [Delete a load balancer](~/docs-ref-autogen/load-balancer/loadbalancers.json#LoadBalancers_Delete)    |  DELETE | Deletes an existing Load balancer |  
| [Get information about a load balancer ](~/docs-ref-autogen/load-balancer/loadbalancers.json#LoadBalancers_Get)    |  GET | Gets a Load balancer. | 
| [List load balancers within a resource group](~/docs-ref-autogen/load-balancer/loadbalancers.json#LoadBalancers_List)   |  GET | Lists all Load balancers in a resource group. |  
| [List load balancers within a subscription](~/docs-ref-autogen/load-balancer/loadbalancers.json#LoadBalancers_ListAll) |  GET | Lists all Load balancers in a subscription. |    

