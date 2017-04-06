---
title: List Azure Application Gateways (GET) | Microsoft Docs
ms.date: 03/29/2017
ms.service: application-gateway
ms.devlang: rest-api
ms.topic: reference
author: amitsriva
ms.author: amsriva
manager: rossort
---
# List application gateways (GET)

Lists all application gateways that belong to a subscription.  

For information about getting started with Azure REST operations including request authentication, see [Azure REST API Reference](../../index.md).

## Request  
  
|Method|Request URI|  
|------------|-----------------|  
|GET|`/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/applicationGateways?api-version={api-version}`|  

| Parameter | Description |
| --------- | ----------- |
| subscriptionId | The identifier of your subscription where the Application Gateways exists. |
| resourceGroupName | The name of the resource group that contains the Application Gateways. |
| api-version | The version of the API to use. The current version is 2016-09-01. | 
  
### Response body  
 A collection of results of the GET on Application Gateway  
  
 **Status code:** If successful, the operation returns HTTP status code of 200(OK).
