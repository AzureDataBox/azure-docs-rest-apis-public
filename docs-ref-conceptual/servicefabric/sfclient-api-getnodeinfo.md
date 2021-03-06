---
title: "Get Node Info"
ms.date: "2018-07-20"
ms.prod: "azure"
ms.service: "service-fabric"
ms.topic: "reference"
applies_to: 
  - "Azure"
  - "Windows Server 2012 R2"
  - "Windows Server 2016"
dev_langs: 
  - "rest-api"
helpviewer_keywords: 
  - "Service Fabric REST API Reference"
author: "rwike77"
ms.author: "ryanwi"
manager: "timlt"
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
# Get Node Info
Gets the information about a specific node in the Service Fabric cluster.

The response includes the name, status, ID, health, uptime, and other details about the node.

## Request
| Method | Request URI |
| ------ | ----------- |
| GET | `/Nodes/{nodeName}?api-version=6.0&timeout={timeout}` |


## Parameters
| Name | Type | Required | Location |
| --- | --- | --- | --- |
| [`nodeName`](#nodename) | string | Yes | Path |
| [`api-version`](#api-version) | string | Yes | Query |
| [`timeout`](#timeout) | integer (int64) | No | Query |

____
### `nodeName`
__Type__: string <br/>
__Required__: Yes<br/>
<br/>
The name of the node.

____
### `api-version`
__Type__: string <br/>
__Required__: Yes<br/>
__Default__: `6.0` <br/>
<br/>
The version of the API. This parameter is required and its value must be '6.0'.

Service Fabric REST API version is based on the runtime version in which the API was introduced or was changed. Service Fabric runtime supports more than one version of the API. This is the latest supported version of the API. If a lower API version is passed, the returned response may be different from the one documented in this specification.

Additionally the runtime accept any version that is higher than the latest supported version up to the current version of the runtime. So if the latest API version is 6.0, but if the runtime is 6.1, in order to make it easier to write the clients, the runtime will accept version 6.1 for that API. However the behavior of the API will be as per the documented 6.0 version.


____
### `timeout`
__Type__: integer (int64) <br/>
__Required__: No<br/>
__Default__: `60` <br/>
__InclusiveMaximum__: `4294967295` <br/>
__InclusiveMinimum__: `1` <br/>
<br/>
The server timeout for performing the operation in seconds. This timeout specifies the time duration that the client is willing to wait for the requested operation to complete. The default value for this parameter is 60 seconds.

## Responses

| HTTP Status Code | Description | Response Schema |
| --- | --- | --- |
| 200 (OK) | A successful operation will return information about the node with the specified nodeName.<br/> | [NodeInfo](sfclient-model-nodeinfo.md) |
| 204 (NoContent) | An empty response is returned if the specified nodeName is not found.<br/> |  |
| All other status codes | The detailed error response.<br/> | [FabricError](sfclient-model-fabricerror.md) |

## Examples

### Get a specific node by node name

This example shows how to get information about an node using it's identifier. If the node is found, information about it is returned with 200 status code. If the node is not found, empty content is returned with 204 status code.

#### Request
```
GET http://localhost:19080/Nodes/_Node_1?api-version=6.0
```

#### 200 Response
##### Body
```json
{
  "Name": "_testnode_0",
  "IpAddressOrFQDN": "10.0.0.4",
  "Type": "testnode",
  "CodeVersion": "6.3.139.9494",
  "ConfigVersion": "5",
  "NodeStatus": "Up",
  "NodeUpTimeInSeconds": "18688",
  "HealthState": "Ok",
  "IsSeedNode": true,
  "UpgradeDomain": "0",
  "FaultDomain": "fd:/0",
  "Id": {
    "Id": "2acb9f55540659b1c95f27cc128ab326"
  },
  "InstanceId": "131738240209152398",
  "NodeDeactivationInfo": {
    "NodeDeactivationIntent": "Invalid",
    "NodeDeactivationStatus": "None",
    "NodeDeactivationTask": [],
    "PendingSafetyChecks": []
  },
  "IsStopped": false,
  "NodeDownTimeInSeconds": "0",
  "NodeUpAt": "2018-06-18T19:33:52.944Z",
  "NodeDownAt": "2018-06-18T19:33:39.514Z"
}
```


#### 204 Response
##### Body
The response body is empty.