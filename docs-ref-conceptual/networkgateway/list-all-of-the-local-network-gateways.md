---
title: "List all of the local network gateways"
ms.custom: ""
ms.date: "05/03/2015"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "virtual-network"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: da65d985-b1d6-4169-8fa4-c7ec227f06ae
caps.latest.revision: 4
author: "yushwang"
ms.author: "yushwang"
manager: "rossort"
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
# List all of the local network gateways
List all of the local network gateways in a resource group.  
  
## Request  
 See [Local Network Gateways ](local-network-gateways.md) for headers and parameters that are used by all requests related to local network gateways.  
  
|Method|Request URI|  
|------------|-----------------|  
|GET|`/subscriptions/{subscriptionId}/resourceGroups/{resource-group-name}/providers/microsoft.network/localnetworkgateways?api-version={api-version}`|  
  
## Response  
 Status code: 200 (OK) if the action is successful; otherwise, 404 (Not Found).  
  
```json  
[  
  {  
  "name": "mylocalgateway1",  
  "id": "/subscriptions/{subscription-id}/resourceGroups/<resourceGroupName>/providers/microsoft.network/localNetworkGateways/mylocalgateway1",  
  "tags": { "key1": "value1" },  
  "etag": "W/\"00000000-0000-0000-0000-000000000000\"",  
  "properties": {  
    "ipAddress": "{ipAddress}",  
    "subnet": [ "{subnetIPAddressPrefix}" ],  
    "vendor": "device vendor",  
    "platform": "device platform",  
    "osFamily": "family"  
    }  
  }  
]  
```  
  
|Element Name|Description|  
|------------------|-----------------|  
|name|The name of the request local network gateway.|  
|ipAddress|The ip address of the local network gateway.|  
|subnet|One of the prefixes that is contained within the local network site.|  
|vendor|The vendor of the vpn device.|  
|platform|The platform of the vpn device.|  
|osFamily|The OS family of the vpn device.|  
|Element Name|Description|
