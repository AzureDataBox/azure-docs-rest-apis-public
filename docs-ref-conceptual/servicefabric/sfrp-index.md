---
title: "Service Fabric Resource Manager REST API Reference"
ms.date: "2017-04-28"
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


# Service Fabric Resource Manager REST API Reference

[Service Fabric](http://aka.ms/ServiceFabric) is a distributed systems platform that makes it easy to package, deploy, and manage scalable and reliable microservices. 

A Service Fabric cluster is a network-connected set of virtual or physical machines into which your microservices are deployed and managed. [Service Fabric Resource Manager APIs](sfrp-index.md) allows you to create and manage Service Fabric cluster in Azure. Once a cluster is created you can manage and deploy microservices based applications and containers in the cluster using [Service Fabric Client APIs](sfclient-index.md).

Following is a list of Service Fabric Resource Manager REST APIs.

---
title: "Service Fabric Resource Manager REST API Reference"
ms.date: "2017-04-28"
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
# Service Fabric Resource Manager REST API Reference


----
# [Cluster APIs](sfrp-index-cluster.md)

| Name | Description |
| --- | --- |
| [Create](sfrp-api-clusters_create.md) | Create a ServiceFabric cluster<br/> |
| [Delete](sfrp-api-clusters_delete.md) | Delete cluster resource<br/> |
| [Get](sfrp-api-clusters_get.md) | Get cluster resource<br/> |
| [Update](sfrp-api-clusters_update.md) | Update cluster configuration<br/> |
| [List By Resource Group](sfrp-api-clusters_listbyresourcegroup.md) | List cluster resource by resource group<br/> |
| [List](sfrp-api-clusters_list.md) | List cluster resource<br/> |

----
# [ClusterVersion APIs](sfrp-index-clusterversion.md)

| Name | Description |
| --- | --- |
| [List](sfrp-api-clusterversions_list.md) | List cluster code versions by location<br/> |

----
# [Operations APIs](sfrp-index-operations.md)

| Name | Description |
| --- | --- |
| [List](sfrp-api-operations_list.md) |  |

----
# [Models](sfrp-index-models.md)

| Name | Description |
| --- | --- |
| [AvailableOperationDisplay](sfrp-model-availableoperationdisplay.md) | Operation supported by ServiceFabric resource provider<br/> |
| [AzureActiveDirectory](sfrp-model-azureactivedirectory.md) | The settings to enable AAD authentication on the cluster<br/> |
| [CertificateDescription](sfrp-model-certificatedescription.md) | Certificate details<br/> |
| [ClientCertificateCommonName](sfrp-model-clientcertificatecommonname.md) | Client certificate details using common name<br/> |
| [ClientCertificateThumbprint](sfrp-model-clientcertificatethumbprint.md) | Client certificate details using thumbprint<br/> |
| [Cluster](sfrp-model-cluster.md) | The cluster resource<br/> |
| [ClusterCodeVersionsListResult](sfrp-model-clustercodeversionslistresult.md) | The list results of the ServiceFabric runtime versions<br/> |
| [ClusterCodeVersionsResult](sfrp-model-clustercodeversionsresult.md) | The result of the ServiceFabric runtime versions<br/> |
| [ClusterHealthPolicy](sfrp-model-clusterhealthpolicy.md) | Defines a health policy used to evaluate the health of the cluster or of a cluster node.<br/> |
| [ClusterListResult](sfrp-model-clusterlistresult.md) | Cluster list results<br/> |
| [ClusterProperties](sfrp-model-clusterproperties.md) | The cluster resource properties<br/> |
| [ClusterPropertiesUpdateParameters](sfrp-model-clusterpropertiesupdateparameters.md) | The cluster resource properties can be updated<br/> |
| [ClusterUpdateParameters](sfrp-model-clusterupdateparameters.md) | Cluster update request<br/> |
| [ClusterUpgradeDeltaHealthPolicy](sfrp-model-clusterupgradedeltahealthpolicy.md) | Delta health policy for the cluster<br/> |
| [ClusterUpgradePolicy](sfrp-model-clusterupgradepolicy.md) | Cluster upgrade policy<br/> |
| [ClusterVersionDetails](sfrp-model-clusterversiondetails.md) | The detail of the ServiceFabric runtime version result<br/> |
| [DiagnosticsStorageAccountConfig](sfrp-model-diagnosticsstorageaccountconfig.md) | Diagnostics storage account config<br/> |
| [EndpointRangeDescription](sfrp-model-endpointrangedescription.md) | Port range details<br/> |
| [ErrorModel](sfrp-model-errormodel.md) | The error detail<br/> |
| [NodeTypeDescription](sfrp-model-nodetypedescription.md) | Describes a node type in the cluster, each node type represents sub set of nodes in the cluster<br/> |
| [OperationListResult](sfrp-model-operationlistresult.md) | Result of the request to list ServiceFabric operations. It contains a list of operations and a URL link to get the next set of results.<br/> |
| [OperationResult](sfrp-model-operationresult.md) | Available operation list result<br/> |
| [Resource](sfrp-model-resource.md) | The resource model definition.<br/> |
| [ServiceTypeDeltaHealthPolicy](sfrp-model-servicetypedeltahealthpolicy.md) | Service health policy<br/> |
| [SettingsParameterDescription](sfrp-model-settingsparameterdescription.md) | ServiceFabric settings under sections<br/> |
| [SettingsSectionDescription](sfrp-model-settingssectiondescription.md) | ServiceFabric section settings<br/> |

