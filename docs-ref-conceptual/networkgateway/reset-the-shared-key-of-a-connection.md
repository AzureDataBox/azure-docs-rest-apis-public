---
title: Reset the shared key of a connection
ms.date: 03/09/2017
ms.service: expressroute
ms.devlang: rest-api
ms.topic: reference
author: yushwang
ms.author: yushwang
manager: rossort
---
# Reset the shared key of a connection&#160;
Resets the shared key for the virtual network gateway connection.  

For information about getting started with Azure REST operations including request authentication, see [Azure REST API Reference](../../../index.md).

## Request  

|Method|Request URI|  
|------------|-----------------|  
|POST|`/subscriptions/{subscriptionId}/resourceGroups/{resource-group-name}/providers/microsoft.network/connections/{connection-name}/sharedkey/reset?api-version={api-version}`|  
  
```json  
{  
   "KeyLength": {shared-key-length}  
}  
```  
  
|Element name|Required|Type|Description|  
|------------------|--------------|----------|-----------------|  
|KeyLength|Yes|String|The length of the shared key.|  
  
## Response  
 Status code: 200 (OK) if the action is successful; otherwise, 404 (Not Found).
