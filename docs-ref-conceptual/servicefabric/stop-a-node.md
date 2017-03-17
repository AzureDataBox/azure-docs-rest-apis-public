---
title: "Stop a node"
ms.custom: ""
ms.date: "2017-03-16"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "service-fabric"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
applies_to: 
  - "Azure"
  - "Windows 10"
  - "Windows 8"
  - "Windows 8.1"
  - "Windows Server 2012 R2"
dev_langs: 
  - "CSharp"
ms.assetid: 0cef0552-a7c4-4c48-ab11-1bffcccefe2a
caps.latest.revision: 3
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
# Stop a node
Stops a Service Fabric cluster node that is in a started state. The node will stay down until [Start a node](start-a-node.md) is called.  
  
## Request  
See [Cluster](cluster.md) for headers and parameters that are used by all requests related to the cluster  
  
|Method|Request URI|  
|------------|-----------------|  
|POST|`<URI>/Nodes/{node-name}/$/Stop?api-version={api-version}`|  

```
{
    "NodeInstanceId":"12345"
}
```

|Element name|Required|Type|Description|
|------------|-----------------|------------|-----------------|  
|NodeInstanceId|Yes|String|The node instance id of the target node.  Find the instance id by doing a node query (see [Get a list of nodes](get-a-list-of-nodes.md).  A value of “0” may be used if you do not care about a specific instance.|
  
## Response  
A successful operation will return 200 OK. For information on error codes, see [Status and Error Codes](status-and-error-codes1.md).

Here is an example of the error if the incorrect instance id is used:

```
{
    "Error": {
        "Code": "FABRIC_E_INSTANCE_ID_MISMATCH",
        "Message": "The provided InstanceId did not match."
    }
}
```