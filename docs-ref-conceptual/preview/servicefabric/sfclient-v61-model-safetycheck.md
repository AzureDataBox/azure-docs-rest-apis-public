---
title: "SafetyCheck"
ms.date: "2018-01-22"
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
# SafetyCheck

Represents a safety check performed by service fabric before continuing with the operations. These checks ensure the availability of the service and the reliability of the state.
# Inheritance

The type 'SafetyCheck' is a base type of the polymorphic type model with property 'Kind' as the discriminator.
Depending upon the value of the property the serialized contents on the wire will be one of the derived types listed below.
## Derived Types

| Kind | Derived Type |
| --- | --- | 
| EnsureSeedNodeQuorum | [SeedNodeSafetyCheck](sfclient-v61-model-seednodesafetycheck.md) |
| EnsureAvailability | [EnsureAvailabilitySafetyCheck](sfclient-v61-model-ensureavailabilitysafetycheck.md) |
| EnsurePartitionQuorum | [EnsurePartitionQurumSafetyCheck](sfclient-v61-model-ensurepartitionqurumsafetycheck.md) |
| WaitForInbuildReplica | [WaitForInbuildReplicaSafetyCheck](sfclient-v61-model-waitforinbuildreplicasafetycheck.md) |
| WaitForPrimaryPlacement | [WaitForPrimaryPlacementSafetyCheck](sfclient-v61-model-waitforprimaryplacementsafetycheck.md) |
| WaitForPrimarySwap | [WaitForPrimarySwapSafetyCheck](sfclient-v61-model-waitforprimaryswapsafetycheck.md) |
| WaitForReconfiguration | [WaitForReconfigurationSafetyCheck](sfclient-v61-model-waitforreconfigurationsafetycheck.md) |

