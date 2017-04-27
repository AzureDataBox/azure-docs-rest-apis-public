---
title: "Unregister Application Type"
ms.date: "2017-04-26"
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
# Unregister Application Type
Removes or unregisters a Service Fabric application type from the cluster.

Removes or unregisters a Service Fabric application type from the cluster. This operation can only be performed if all application instance of the application type has been deleted. Once the application type is unregistered, no new application instance can be created for this particular application type.

## Request
| Method | Request URI |
| ------ | ----------- |
| POST | `/ApplicationTypes/{applicationTypeName}/$/Unprovision?api-version=3.0` |


## Parameters
| Name | Type | Required | Location |
| --- | --- | --- | --- |
| [applicationTypeName](#applicationtypename) | string | Yes | Path |
| [api-version](#api-version) | string | Yes | Query |
| [ApplicationTypeImageStoreVersion](#applicationtypeimagestoreversion) | [ApplicationTypeImageStoreVersion](model-ApplicationTypeImageStoreVersion.md) | Yes | Body |

____
### applicationTypeName
__Type__: string <br/>
__Required__: Yes<br/>
<br/>
The name of the application type.

____
### api-version
__Type__: string <br/>
__Required__: Yes<br/>
__Default__: 3.0 <br/>
<br/>
The version of the API. This is a required parameter and it's value must be "3.0".

____
### ApplicationTypeImageStoreVersion
__Type__: [ApplicationTypeImageStoreVersion](model-ApplicationTypeImageStoreVersion.md) <br/>
__Required__: Yes<br/>
<br/>
The version of the application type in the image store.

## Responses

| HTTP Status Code | Description | Response Schema |
| --- | --- | --- |
| 200 (OK) | A successful unprovision will return 200 status code.<br/> |  |
| All other status codes | The detailed error response.<br/> | [FabricError](model-FabricError.md) |
