---
title: "Query the status of a troubleshoot request on a resource"
ms.date: 2017-01-30
ms.prod: azure
ms.service: network-watcher
ms.topic: reference
ms.assetid: 
author: gwallace
manager: timlt
---

# Query the status of a troubleshoot request on a resource

Queries the status of the last completed troubleshoot request.

For information about getting started with Azure REST operations including request authentication, see [Azure REST API Reference](../../../../index.md).

## Request

| HTTP Method | URI|  
| ----------- |----|  
| POST | `/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/networkWatchers/{networkWatcherName}/queryTroubleshootResult?api-version={api-version}` |

```json
{ 
"TargetResourceId": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/connections/{connectionName}" 
}
```

## Response  

The response includes an HTTP status code and a set of response headers.

### Success codes

| Code | Description |
| ---- | ----------- |
| **200 (OK)** | The troubleshoot result is available for TargetResourceId. | 
| **202 (Accepted)** | The troubleshoot operation is in progress for TargetResourceId. | 

### VirtualNetworkGateway
```json
{ 
"startTime": "2017-01-12T00:19:47.0442834Z", 
"endTime": "2017-01-12T00:20:09.914Z", 
"code": "UnHealthy", 
"results": [ 
  { 
    "id": "VipUnResponsive", 
    "summary": "We are sorry, your VPN gateway is unreachable from the Internet", 
    "detail": "During this time S2S VPN tunnels to on premises sites or other Azure virtual networks will be disconnected", 
    "recommendedActions": [ 
      { 
        "actionText": "Verify if there is a network security group (NSG) applied to the GatewaySubnet", 
        "actionUri": "https://docs.microsoft.com/en-us/azure/virtual-network/virtual-networks-create-nsg-arm-pportal",
        "actionUriText": "Verify" 
      }, 
      { 
        "actionText": "If your VPN gateway isn't up and running by the expected resolution time, contact support", 
        "actionUri": "http://azure.microsoft.com/support", 
        "actionUriText": "contact support"
      } 
    ] 
  } 
] 
}
```

### Connection

```json
{ 
"startTime": "2017-01-12T00:19:23.2005008Z", 
"endTime": "2017-01-12T00:25:01.272Z", 
"code": "UnHealthy", 
"results": [ 
  { 
    "id": "PeerReachability", 
    "summary": "The connection cannot be established because the other VPN device is unreachable", 
    "detail": "If the on-premises VPN device is unreachable or not responding to the Azure VPN gateway IKE handshake, the VPN connection cannot establish", 
    "recommendedActions": [ 
      { 
        "actionText": "Verify if the public IP address of the corresponding Azure Local Network Gateway is configured correctly", 
        "actionUri": "https://azure.microsoft.com/en-us/documentation/articles/vpn-gateway-modify-local-network-gateway/", 
        "actionUriText": "Verify if the public IP address" 
      }, 
      { 
        "actionText": "Verify the configuration of your on-premises VPN device so it allows your Azure VPN gateway to establish connections", 
        "actionUri": "https://azure.microsoft.com/en-us/documentation/articles/vpn-gateway-about-vpn-devices/", 
        "actionUriText": "Verify the configuration" 
      }, 
      { 
        "actionText": "Verify if there is a network security group (NSG) applied to the GatewaySubnet", 
        "actionUri": "https://docs.microsoft.com/en-us/azure/virtual-network/virtual-networks-create-nsg-arm-pportal", 
        "actionUriText": "Verify the configuration" 
      }, 
      { 
        "actionText": "If you are experiencing problems you believe are caused by Azure, contact support", 
        "actionUri": "http://azure.microsoft.com/support", 
        "actionUriText": "contact support"
      } 
    ] 
  } 
] 
}
```

### Error codes

| Code | Description |
| ---- | ----------- |
| **400 BadRequest** | No troubleshoot operation state exists for the specified TargetResourceId.| 
| **403 Forbidden** | Caller doesn’t have the privilege to call this API. |
| **404 NotFound** | No troubleshoot operation state exists for the specified TargetResourceId. |
| **500 Internal Server Error** |  A server-side error has happened. Retry the operation. |     



 
