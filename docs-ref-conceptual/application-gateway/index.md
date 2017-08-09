---
title: Azure Application Gateway REST API | Microsoft Docs
ms.date: 08/08/2017
ms.service: application-gateway
ms.devlang: rest-api
ms.topic: reference
author: amitsriva
ms.author: amsriva
manager: rossort
---

# Application Gateway REST API

Application Gateway is a Network Service which provides HTTP Load balancing as a Service to Azure customers. This is a fully managed service implemented as dedicated Hosted Service in a subscription owned by Gateway Manager but deployed in customer vnet. In addition to basic HTTP Load balancing, it provides other Layer 7 features like Cookie based client affinity and SSL offload, URL routing and multi-site hosting.

## REST Operations

| Operation | REST Verb | Description | 
|---------|---------|-----------|
| [Backend health](~/docs-ref-autogen/application-gateway/ApplicationGateways.json#ApplicationGateways_BackendHealth)|POST|Gets the backend health of the specified application gateway in a resource group.|
| [Create or update an application gateway](~/docs-ref-autogen/application-gateway/ApplicationGateways.json#ApplicationGateways_CreateOrUpdate) |  PUT | Creates or updates an application gateway |  
| [Delete an application gateway](~/docs-ref-autogen/application-gateway/ApplicationGateways.json#ApplicationGateways_Delete) |  DELETE | Deletes an existing application gateway. |  
| [Get an application gateway](~/docs-ref-autogen/application-gateway/ApplicationGateways.json#ApplicationGateways_Get) |  GET | Gets details on an application gateway. |  
| [List application gateways](~/docs-ref-autogen/application-gateway/ApplicationGateways.json#ApplicationGateways_List) |  GET | Lists all application gateways in a resource group. | 
| [List all application gateways](~/docs-ref-autogen/application-gateway/ApplicationGateways.json#ApplicationGateways_ListAll) |  GET | Lists all application gateways. | 
| [Start an application gateway](~/docs-ref-autogen/application-gateway/ApplicationGateways.json#ApplicationGateways_Start) |  POST | Starts an application gateway. |  
| [Stop an application gateway](~/docs-ref-autogen/application-gateway/ApplicationGateways.json#ApplicationGateways_Stop) |  POST | Stops an application gateway. | 
| [Get available rule sets (WAF)](~/docs-ref-autogen/application-gateway/ApplicationGateways.json#ApplicationGateways_ListAvailableWafRuleSets) |GET | Gets a list of available WAF rule sets.|
| [List available SSL options](~/docs-ref-autogen/application-gateway/ApplicationGateways.json#ApplicationGateways_ListAvailableSslOptions) |GET | Lists available SSL options for configuring SSL policy.|
| [List available SSL predefined policies](~/docs-ref-autogen/application-gateway/ApplicationGateways.json#ApplicationGateways_ListAvailableSslPredefinedPolicies) |GET | Lists all SSL predefined policies for configuring SSL policy.|
