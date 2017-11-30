---
title: "Patch"
ms.date: "2017-11-30"
ms.prod: "azure"
ms.service: "service-fabric"
ms.topic: "reference"
applies_to: 
  - "Azure"
dev_langs: 
  - "rest-api"
helpviewer_keywords: 
  - "Service Fabric Resource Manager REST API Reference"
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
# Patch

Updates an application resource with the specified name.

## Request
| Method | Request URI |
| ------ | ----------- |
| PATCH | `/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ServiceFabric/clusters/{clusterName}/applications/{applicationName}?api-version=2017-07-01-preview` |


## Parameters
| Name | Type | Required | Location |
| --- | --- | --- | --- |
| [subscriptionId](#subscriptionid) | string | Yes | Path |
| [resourceGroupName](#resourcegroupname) | string | Yes | Path |
| [clusterName](#clustername) | string | Yes | Path |
| [applicationName](#applicationname) | string | Yes | Path |
| [api-version](#api-version) | string | Yes | Query |
| [parameters](#parameters) | [ApplicationResourceUpdate](sfrp-2017-07-01-preview-model-applicationresourceupdate.md) | Yes | Body |

____
### subscriptionId
__Type__: string <br/>
__Required__: Yes<br/>
<br/>
The customer subscription identifier

____
### resourceGroupName
__Type__: string <br/>
__Required__: Yes<br/>
<br/>
The name of the resource group.

____
### clusterName
__Type__: string <br/>
__Required__: Yes<br/>
<br/>
The name of the cluster resource

____
### applicationName
__Type__: string <br/>
__Required__: Yes<br/>
<br/>
The name of the application resource.

____
### api-version
__Type__: string <br/>
__Required__: Yes<br/>
__Default__: 2017-07-01-preview <br/>
<br/>
The version of the API. This is a required parameter and it's value must be "2017-07-01-preview" for this specification.

____
### parameters
__Type__: [ApplicationResourceUpdate](sfrp-2017-07-01-preview-model-applicationresourceupdate.md) <br/>
__Required__: Yes<br/>
<br/>
The application resource for patch operations.

## Responses

| HTTP Status Code | Description | Response Schema |
| --- | --- | --- |
| 202 (Accepted) | The request was accepted and the operation will complete asynchronously.<br/> | [ApplicationResourceUpdate](sfrp-2017-07-01-preview-model-applicationresourceupdate.md) |
| All other status codes | The detailed error response.<br/> | [ErrorModel](sfrp-2017-07-01-preview-model-errormodel.md) |

## Examples

### Patch an application

#### Request
```
PATCH https://management.azure.com/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/resRg/providers/Microsoft.ServiceFabric/clusters/myCluster/applications/myApp?api-version=2017-07-01-preview
```

##### Body
```json
{
  "type": "applications",
  "location": "eastus",
  "id": "/subscriptions/00000000-0000-0000-0000-000000000000/resourcegroups/resRg/providers/Microsoft.ServiceFabric/clusters/myCluster/applications/myApp",
  "name": "myCluster",
  "tags": {},
  "properties": {
    "typeName": "myAppType",
    "typeVersion": "1.0",
    "removeApplicationCapacity": false,
    "metrics": [
      {
        "name": "metric1",
        "reservationCapacity": 1,
        "maximumCapacity": 3,
        "totalApplicationCapacity": 5
      }
    ]
  }
}
```

#### 202 Response
##### Headers
```html
Retry-After: 10
Location: http://10.91.140.224/subscriptions/00000000-0000-0000-0000-000000000000/providers/Microsoft.ServiceFabric/locations/eastus/operationResults/0dbcd38e-7d2e-4751-89ac-24422bce8eca?api-version=2017-07-01-preview
```

##### Body
```json
{
  "type": "applications",
  "location": "eastus",
  "id": "/subscriptions/00000000-0000-0000-0000-000000000000/resourcegroups/resRg/providers/Microsoft.ServiceFabric/clusters/myCluster/applications/myApp",
  "name": "myCluster",
  "tags": {},
  "etag": "W/\"636461852503679536\"",
  "properties": {
    "provisioningState": "Updating",
    "typeName": "myAppType",
    "typeVersion": "1.0",
    "removeApplicationCapacity": false,
    "metrics": [
      {
        "name": "metric1",
        "reservationCapacity": 1,
        "maximumCapacity": 3,
        "totalApplicationCapacity": 5
      }
    ]
  }
}
```
