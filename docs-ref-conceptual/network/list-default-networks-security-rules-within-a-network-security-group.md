---
title: "List default networks security rules within a network security group"
ms.custom: ""
ms.date: "2015-11-04"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "virtual-network"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: b52671f1-0739-4ab3-a3fb-bcbe9382b079
caps.latest.revision: 8
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
# List default networks security rules within a network security group
## Request  
 See [Common parameters and headers](network-security-rules.md#bk_common) for headers and parameters that are used by all requests related to network security rules.  
  
|Method|Request URI|  
|------------|-----------------|  
|GET|`https://management.azure.com/subscriptions/{subscription-id}/resourceGroups/{resource-group-name}/providers/Microsoft.Network/networkSecurityGroups/{network-security-group-name}/defaultSecurityRules?api-version={api-version}`|  
  
 Replace {network-security-group-name} with the name of the network security group whose default rules you wish to list.  
  
## Response  
 **Status code:** 200  
  
```json  
[  
   {  
      "name": "rule1",  
      "id": "/subscriptions/{guid}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/networkSecurityGroups/myNsg/securityRules/rule1",  
      "etag": "W/\"00000000-0000-0000-0000-000000000000\"",  
      "properties": {  
         "provisioningState": "Succeeded",  
         "description": "description-of-this-rule",  
         "protocol": "*",  
         "sourcePortRange": "source-port-range",  
         "destinationPortRange": "destination-port-range",  
         "sourceAddressPrefix": "*",  
         "destinationAddressPrefix": "*",  
         "access": "Allow",  
         "priority": priority-of-the-rule,  
         "direction": "Inbound"  
      }  
   }  
]   
```  
  
|Element name|Description|  
|------------------|-----------------|  
|description|A description for this rule. Restricted to 140 characters.|  
|protocol|Network protocol this rule applies to.|  
|sourcePortRange|Source Port or Range.|  
|destinationPortRange|Destination Port or Range.|  
|sourceAddressPrefix|CIDR or source IP range or * to match any IP.|  
|destinationAddressPrefix|CIDR or destination IP range or * to match any IP.|  
|access|Specifies whether network traffic is allowed or denied.|  
|priority|Specifies the priority of the rule.|  
|direction|The direction specifies if rule will be evaluated on incoming or outgoing traffic.|
