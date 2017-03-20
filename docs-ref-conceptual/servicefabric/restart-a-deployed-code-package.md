---
title: "Restart a deployed code package"
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
ms.assetid: 5fc8fcd1-3c14-4302-9de7-072c38b68ffe
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
# Restart a deployed code package
Restarts a code package deployed on a node in a cluster. This aborts the code package process, which will restart all the user service replicas hosted in that process.  
  
## Request  
 See [Application type](application-type.md) for headers and parameters that are used by all requests related to code packages.  
  
|Method|Request URI|  
|------------|-----------------|  
|POST|`<URI>/Nodes/{node-name}/$/GetApplication/{Application-name}/$/GetCodePackages/$/Restart?api-version={api-version}`|  
```
{
  "ServiceManifestName" : "SP1",
  "CodePackageName" : "CP1",
  "CodePackageInstanceId" : "131315916073905279"
}
```

|Element name|Description|
|------------|-----------------|
|ServiceManifestName|The service manifest name.|
|CodePackageName|The name of the code package to target|
|CodePackageInstanceId|The instance id of the code package to target.|

The required information above can be found from a deployed code package query.  See [Get a list of code packages](get-a-list-of-code-packages.md).
  
## Response  
 A successful operation will return 200 OK. For information on error codes, see [Status and Error Codes](status-and-error-codes1.md).