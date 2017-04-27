---
title: "ReplicaHealthState"
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
# ReplicaHealthState

Represents a base class for stateful service replica or stateless service instance health state.

## Properties
| Name | Type | Required |
| --- | --- | --- |
| [AggregatedHealthState](#aggregatedhealthstate) | string (enum) | No |
| [ServiceKind](#servicekind) | string (enum) | No |
| [PartitionId](#partitionid) | string (uuid) | No |

____
### AggregatedHealthState
__Type__: string (enum) <br/>
__Required__: No<br/>
<br/>
The health state of a Service Fabric entity such as Cluster, Node, Application, Service, Partition, Replica etc.

  - Invalid - Indicates an invalid health state. All Service Fabric enumerations have the invalid type. The value is zero.
  - Ok - Indicates the health state is okay. The value is 1.
  - Warning - Indicates the health state is at a warning level. The value is 2.
  - Error - Indicates the health state is at an error level. Error health state should be investigated, as they can impact the correct functionality of the cluster. The value is 3.
  - Unknown - Indicates an unknown health status. The value is 65535.


____
### ServiceKind
__Type__: string (enum) <br/>
__Required__: No<br/>
<br/>
The kind of service (Stateless or Stateful). Following are the possible values.

- Invalid - Indicates the service kind is invalid. All Service Fabric enumerations have the invalid type. The value is zero.
- Stateless - Does not use Service Fabric to make its state highly available or reliable. The value is 1.
- Stateful - Uses Service Fabric to make its state or part of its state highly available and reliable. The value is 2.


____
### PartitionId
__Type__: string (uuid) <br/>
__Required__: No<br/>
<br/>
Id of the partition to which this replica belongs.
