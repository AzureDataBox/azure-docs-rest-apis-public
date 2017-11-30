---
title: "SingletonPartitionSchemeDescription"
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
# SingletonPartitionSchemeDescription

Describes the partition scheme of a singleton-partitioned, or non-partitioned service.

## Properties
| Name | Type | Required |
| --- | --- | --- |
| [PartitionScheme](#partitionscheme) | string | Yes |

____
### PartitionScheme
__Type__: string <br/>
__Required__: Yes <br/>
<br/>
A discriminator property. Its value must be 'Singleton' for objects of type 'SingletonPartitionSchemeDescription'.