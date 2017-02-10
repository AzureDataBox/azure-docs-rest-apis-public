---
title: "Create or update a network security group"
ms.custom: ""
ms.date: "2016-04-27"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "virtual-network"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: cc313420-1a08-410d-9944-a11682987a57
caps.latest.revision: 12
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
# Create or update a network security group
## Request  
 See [Common parameters and headers](network-security-groups.md#bk_common) for headers and parameters that are used by all requests related to network security groups.  
  
|Method|Request URI|  
|------------|-----------------|  
|PUT|`https://management.azure.com/subscriptions/{subscription-id}/resourceGroups/{resource-group-name}/providers/Microsoft.Network/networkSecurityGroups/{network-security-group-name}?api-version={api-version}`|  
  
 Replace {network-security-group-name} with the name of the network security group which you want to create or update.  
  
```json  
{   
   "location":"North US",  
   "tags":{   
      "key":"value"  
   },  
   "properties":{   
      "securityRules":[   
         {   
            "name":"myNsRule",  
            "properties":{   
               "description":"description-of-this-rule",  
               "protocol": "Tcp",  
               "sourcePortRange":"source-port-range",  
               "destinationPortRange":"destination-port-range",  
               "sourceAddressPrefix":"*",  
               "destinationAddressPrefix":"*",  
               "access":"Allow",  
               "priority":priority-of-the-rule,  
               "direction":"Inbound"  
            }  
         }  
      ]  
   }  
}  
  
```  
  
|Element name|Required|Type|Description|  
|------------------|--------------|----------|-----------------|  
|location|Yes|String|Specifies the supported Azure location of the Network Security Group. For more information, see List all of the available geo-locations.|  
|tags|No|Complex Type|The tags and their values that are used by the Network Security Group.|  
|securityRules|Yes|Complex Type|A collection of Network Security Rules within this Network Security Group.|  
  
## Response  
 **Status code:** 200.  
  
```json  
{    
   "name":"myNsg",  
   "id":"/subscriptions/{guid}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/networkSecurityGroups/myNsg",  
   "location":"North US",  
   "tags":{    
      "key":"value"  
   },  
   "etag":"W/\"00000000-0000-0000-0000-000000000000\"",  
   "properties":{  
      "resourceGuid":"AF6A2C41-9F74-46B3-9F65-F5286FFEE3DE",    
      "provisioningState":"Succeeded",        
      "securityRules":[    
         {    
            "name":"myNsRule",  
            "id":"/subscriptions/{guid}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/networkSecurityGroups/myNsg/securityRules/myNsRule",  
            "etag":"W/\"00000000-0000-0000-0000-000000000000\"",  
            "properties":{    
               "provisioningState":"Succeeded",  
               "description":"description-of-this-rule",  
               "protocol": "*",  
               "sourcePortRange":"source-port-range",  
               "destinationPortRange":"destination-port-range",  
               "sourceAddressPrefix":"*",  
               "destinationAddressPrefix":"*",  
               "access":"Allow",  
               "priority":priority-of-the-rule,  
               "direction":"Inbound",  
  
            }  
         }  
      ],  
      "defaultSecurityRules":[    
         {    
            "name":"AllowVnetInBound",  
            "id":"/subscriptions/{guid}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/networkSecurityGroups/myNsg/defaultSecurityRules/AllowVnetInBound",  
            "etag":"W/\"00000000-0000-0000-0000-000000000000\"",  
            "properties":{    
               "provisioningState":"Succeeded",  
               "description":"description-of-this-rule",  
               "protocol": "*",  
               "sourcePortRange":"*",  
               "destinationPortRange":"*",  
               "sourceAddressPrefix":"VirtualNetwork",  
               "destinationAddressPrefix":"VirtualNetwork",  
               "access":"Allow ",  
               "priority":65000,  
               "direction":"Inbound"  
            }  
         }  
      ],  
      "networkInterfaces":[    
         {    
            "id":"/subscriptions/{guid}/resourceGroups/myrg1/providers/Microsoft.Network/networkInterfaces/vm1nic1 "  
         }         {    
            "id":"/subscriptions/{guid}/resourceGroups/myrg1/providers/Microsoft.Network/networkInterfaces/vm1nic2"  
         }  
      ],  
      "subnets":[    
         {    
            "id":"/subscriptions/{guid}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/virtualNetworks/myvnet1/subnets/mysubnet1"  
         }  
      ]  
   }  
}  
```  
  
|Element name|Description|  
|------------------|-----------------|  
|name|The name of the Network Security Group.|  
|id|The identifying URL of the Network Security Group.|  
|location|Specifies the supported Azure location of the Network Security Group. For more information, see List all of the available geo-locations.|  
|tags|The tags and their values that are used by the Network Security Group.|  
|etag|System generated meta-data enabling concurrency control.|  
|resourceGuid|System generated unique identifier used for internal correlation and logging purpose by the platform|  
|provisioningState|Provisioning state of the Network Security Group.|  
|securityRules|A collection of Network Security Rules within this Network Security Group.|  
|defaultSecurityRules|A collection of Default Network Security Rules within this Network Security Group|  
|networkInterfaces.id|A collection of references to Network Interface Cards that reference this Network Security Group.|  
|Subnets.id|A collection of references to Subnets that reference this Network Security Group.|  
  
## Remarks  
 For more information about Network Security Rules, see [Get information about a default network security rule ](get-information-about-a-default-network-security-rule.md).
