---
title: List virtual networks within a subscription
ms.date: 03/15/2017
ms.service: virtual-network
ms.topic: reference
ms.devlang: rest
author: anavinahar 
ms.author: annahar 
ms.manager: narayan
---
# List virtual networks within a subscription

This operation lists all virtual networks in a subscription

For information about getting started with Azure REST operations including request authentication, see [Azure REST API Reference](../../../index.md).

## Request  
  
|Method|Request URI|  
|------------|-----------------|  
|GET|`/subscriptions/{subscriptionId}/ providers/Microsoft.Network/virtualnetworks?api-version={api-version}`|  

| Parameter | Description |
| --------- | ----------- |
| subscriptionId | The identifier of your subscription where the virtual network peering exists. |
| api-version | The version of the API to use. The current version is 2016-09-01. | 

## Response  
 **Status code:** 200  
  
```json  
[   
   {   
      "name":" myvnet1",  
      "id":"/subscriptions/{subscriptionId}/resourceGroups/mygroup1/providers/Microsoft.Network/virtualNetworks/myvnet1",  
      "location":"North US",  
      "tags":{   
         "key":"value"  
      },  
      "etag":"W/\"00000000-0000-0000-0000-000000000000\"",  
      "properties":{   
         "resourcesubscriptionId":"FA0F0F1A-158F-4725-ACCE-C7B6D5CD937F",  
         "provisioningState":"Succeeded",           
         "addressSpace":{   
            "addressPrefixes":[   
               "10.1.0.0/16",  
               "10.2.0.0/16"  
            ]  
         },  
         "dhcpOptions":{   
            "dnsServers":[   
               "10.1.0.5",  
               "10.1.0.6"  
            ]  
         }           
         "subnets":[   
            {   
               "name":"mysubnet1",  
               "id":"/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/virtualNetworks/myvnet1/subnets/mysubnet1",  
               "etag":"W/\"00000000-0000-0000-0000-000000000000\"",  
               "properties":{   
                  "provisioningState":"Succeeded",  
                  "addressPrefix":"10.1.0.0/24",  
                  "networkSecurityGroup":{   
                     "id":"/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/networkSecurityGroups/myNSG1"  
                  },  
                  "ipConfigurations":[   
                     {   
                        "id":"/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/networkInterfaces/vm1nic1/ipConfigurations/ip1"  
                     },  
                     {   
                        "id":"/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/loadBalancers/lb1/frontendIpConfigurations/ip1"  
                     },  
                     {   
                        "id":"/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/vpnGateways/gw1/ipConfigurations/ip1"  
                     }  
                  ]  
               }  
            }  
         ]  
      }  
   }  
]  
```  
  
|Element name|Description|  
|------------------|-----------------|  
|id|The identifying URL of the Virtual Network.|  
|name|The name of the Virtual Network.|  
|type|Specifies that this is of type Microsoft.Network/virtualNetworks|  
|location|Specifies the supported Azure location of the Virtual Network. For more information, see List all of the available geo-locations|  
|tags|The tags and their values that are used by the Virtual Network.|  
|etag|System generated meta-data enabling concurrency control|  
|resourcesubscriptionId|System generated unique identifier used for internal correlation and logging purpose by the platform|  
|provisioningState|Provisioning state of the Virtual Network|  
|addressSpace|AddressSpace contains an array of IP address ranges that can be used by subnets of the virtual network.|  
|addressSpace.addressPrefixes|List of address blocks reserved for this virtual network in CIDR notation|  
|dhcpOptions|DhcpOptions contains an array of DNS servers available to VMs deployed in the virtual network.|  
|dhcpOptions.dnsServers|List of DNS servers IP addresses.|  
|subnets|Collection of subnets contained within this Virtual Network|  
  
## Remarks  
 For more information about subnets, see [Get information about a subnet](get-information-about-a-subnet.md).
