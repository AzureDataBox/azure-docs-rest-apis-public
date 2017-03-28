---
title: "Application Gateway REST"
ms.custom: ""
ms.date: "2016-02-17"
ms.prod: "azure"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: ed66e2e5-ed60-4d12-ac1e-a8e215395a57
caps.latest.revision: 4
author: "georgewallace"
ms.author: "gwallace"
manager: "carmonm"
translation.priority.mt: 
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pt-br"
  - "ru-ru"
  - "zh-cn"
  - "zh-tw"
---
# Application Gateway REST
Application Gateway is a Network Service which provides HTTP Load balancing as a Service to Azure customers. This is a fully managed service implemented as dedicated Hosted Service in a subscription owned by Gateway Manager but deployed in customer vnet. In addition to basic HTTP Load balancing, it provides other Layer 7 features like Cookie based client affinity and SSL offload, URL routing and multi-site hosting.  

## REST Operations

| Operation | REST Verb | Description | 
|---------|---------|-----------|
| [Create or update an application gateway](create-or-update-an-application-gateway.md) |  PUT | Creates or updates an application gateway |  
| [Delete an application gateway](delete-application-gateway.md) |  DELETE | Deletes an existing application gateway. |  
| [Get an application gateway](get-application-gateway.md) |  GET | Gets details on an application gateway. |  
| [List application gateways](list-application-gateways.md) |  GET | Lists all application gateways. | 
| [Start an application gateway](start-application-gateway.md) |  POST | Starts an application gateway. |  
| [Stop an application gateway](stop-application-gateway.md) |  POST | Stops an application gateway. | 
| [Get available rule sets (WAF)](application-gateway-get-waf-rules.md) |GET | Gets a list of available WAF rule sets.|


