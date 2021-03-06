---
title: "FileVersion"
ms.date: "2018-04-23"
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
# FileVersion

Information about the version of image store file.

## Properties
| Name | Type | Required |
| --- | --- | --- |
| [`VersionNumber`](#versionnumber) | string | No |
| [`EpochDataLossNumber`](#epochdatalossnumber) | string | No |
| [`EpochConfigurationNumber`](#epochconfigurationnumber) | string | No |

____
### `VersionNumber`
__Type__: string <br/>
__Required__: No<br/>
<br/>
The current image store version number for the file is used in image store for checking whether it need to be updated.

____
### `EpochDataLossNumber`
__Type__: string <br/>
__Required__: No<br/>
<br/>
The epoch data loss number of image store replica when this file entry was updated or created.

____
### `EpochConfigurationNumber`
__Type__: string <br/>
__Required__: No<br/>
<br/>
The epoch configuration version number of the image store replica when this file entry was created or updated.
