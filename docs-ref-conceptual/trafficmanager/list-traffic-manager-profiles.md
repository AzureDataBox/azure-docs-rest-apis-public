---
title: "List Traffic Manager profiles"
ms.custom: ""
ms.date: "2016-02-01"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "traffic-manager"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: c6cbd933-eaab-4349-8097-69da55aaa76e
caps.latest.revision: 8
ms.author: "cherylmc"
manager: "carolz"
---
# List Traffic Manager profiles
List Traffic Manager profiles within a resource group.  

## Request  
 See [Common parameters and headers](traffic-manager-profiles-and-endpoints.md#bk_common) for headers and parameters that are used by all requests related to Traffic Manager profiles and endpoints.  

|Method|Request URI|  
|------------|-----------------|  
|GET|`/subscriptions/{subscriptionId}/resourceGroups/{resource-group-name}/providers/Microsoft.Network/trafficManagerProfiles?api-version={api-version}`|  

## Response  
 **Status code:** 200 OK.  

```json  
{   
   "value":[   
      {   
         "id":"/subscriptions/{subsctiption-id}/resourceGroups/{resource-group-name}/Microsoft.Network/trafficManagerProfiles/{profile-name}",  
         "name": "{profile-name}",  
         "type": "Microsoft.Network/trafficManagerProfiles",  
         "location": "global",  
         "tags": {  },  
         "properties": {   
            "profileStatus": "Enabled",  
            "trafficRoutingMethod": "Performance",  
            "dnsConfig": {   
               "relativeName": "myapp",  
               "fqdn": "myapp.trafficmanager.net",  
               "ttl": 30  
            },  
            "monitorConfig": {   
               "profileMonitorStatus": "Online",  
               "protocol": "http",  
               "port": 80,  
               "path": "/monitorpage.aspx"  
            },  
      "endpoints": [   
         {  
            "id": "{ARM resource ID of this endpoint}",  
            "name": "{endpoint-name}",  
            "type": "Microsoft.Network/trafficManagerProfiles/azureEndpoints",  
            "properties": {  
               "endpointStatus": "Enabled",  
               "endpointMonitorStatus": "Online"  
               "targetResourceId": "{resource ID of target resource in Azure}",  
               "target": "myapp.azurewebsites.net",  
               "weight": 10,  
               "priority": 3,  
               "endpointLocation": "centralus"  
            }  
         },  
         {   
            "id": "{ARM resource ID of this endpoint}",  
            "name": "{endpoint-name}",  
            "type": "Microsoft.Network/trafficManagerProfiles/externalEndpoints",  
            "properties": {   
               "endpointStatus": "Enabled",  
               "endpointMonitorStatus": "Online"  
               "target": "myendpoint.contoso.com",  
               "weight": 10,  
               "priority": 5,  
               "endpointLocation": "northeurope",  
            }  
         },  
         {  
            "id": "{ARM resource ID of this endpoint}",  
            "name": "{endpoint-name}",  
            "type": "Microsoft.Network/trafficManagerProfiles/nestedEndpoints",  
            "properties": {  
               "endpointStatus": "Enabled",  
               "endpointMonitorStatus": "Online",  
               "targetResourceId": "{resource ID of child Traffic Manager profile}",  
               "weight": 10,  
               "priority": 1,  
               "endpointLocation": "westeurope",  
               "minChildEndpoints": 1,  
             }  
         }  
      ]  
         },  
         {   
            <...additional profiles...>  
         }  
      ]  
   }  

```  

|Element name|Description|  
|------------------|-----------------|  
|profileStatus|Specifies whether the profile should be enabled or disabled.<br /><br /> Possible values are:<br /><br /> -   Enabled<br />-   Disabled|  
|trafficRoutingMethod|Specifies the traffic routing method, used to determine which endpoint is returned in response to incoming DNS queries.<br /><br /> Possible values are:<br /><br /> -   Performance<br />-   Weighted<br />-   Priority<br />-   Geographic|  
|dnsConfig|Container for DNS settings for this Traffic Manager profile.|  
|relativeName|Specifies the relative DNS name provided by this Traffic Manager profile.|  
|fqdn|The fully-qualified domain name of the Traffic Manager profile. This is a read-only property, formed from the concatenation of the relativeName with the DNS domain used by Azure Traffic Manager.|  
|ttl|Specifies the DNS Time-to-Live (TTL), in seconds.|  
|monitorConfig|Container for endpoint monitoring settings for this Traffic Manager profile.|  
|profileMonitorStatus|Indicates the overall health status for the Traffic Manager profile.<br /><br /> This is a read-only property.  Possible values are:<br /><br /> -   Online<br />-   Degraded<br />-   Inactive<br />-   Disabled<br />-   CheckingEndpoints<br /><br /> See [About Traffic Manager Monitoring](https://azure.microsoft.com/documentation/articles/traffic-manager-monitoring/) for further details.|  
|protocol|Specifies the protocol to use to monitor endpoint health.|  
|port|Specifies the TCP port used to monitor endpoint health.|  
|path|Specifies the path relative to the endpoint domain name used to probe for endpoint health.|  
|endpoints|Specifies an array of Traffic Manager endpoints.|  
|id (within ‘endpoints’ list)|Specifies the ARM resource ID of the endpoint.  Each endpoint is a child resource of the parent profile resource, hence each endpoint has a unique ARM resource ID.|  
|name|Specifies the name (ARM resource name) of the endpoint.|  
|type|Specifies the type of the endpoint.|  
|properties|Container for settings relating to this Traffic Manager endpoint.|  
|target|The fully-qualified DNS name of the endpoint. Traffic Manager returns this value in DNS responses when it directs traffic to this endpoint.  Applicable to endpoints of type ‘AzureEndpoints’ and ‘ExternalEndpoints’ only.|  
|targetResourceId|For endpoints of type ‘AzureEndpoints’, this specifies resource ID of the resource in Azure that this endpoint will direct traffic to.<br /><br /> For endpoints of type ‘NestedEndpoints’, this specifies the resource ID of the child profile that this endpoint will direct traffic to.<br /><br /> This parameter is not applicable to endpoints of type ‘ExternalEndpoints’.|  
|endpointStatus|Specifies the status of the endpoint. If the endpoint is Enabled, it is probed for endpoint health and is included in the traffic routing method.<br /><br /> Possible values are:<br /><br /> -   Enabled<br />-   Disabled|  
|weight|Specifies the weight assigned by Traffic Manager to the endpoint.|  
|priority|Specifies the priority of this endpoint when using the ‘Priority’ traffic routing method.|  
|endpointLocation|Specifies the location of the endpoint.  This value is used in the ‘Performance’ traffic-routing method when determining which endpoint is closest to the end user.|  
|endpointMonitorStatus|Indicates the health status for the endpoint.<br /><br /> This is a read-only property.  Possible values are:<br /><br /> -   Online<br />-   Degraded<br />-   Inactive<br />-   Disabled<br />-   Stopped<br />-   CheckingEndpoint<br /><br /> See [About Traffic Manager Monitoring](https://azure.microsoft.com/documentation/articles/traffic-manager-monitoring/) for further details.|  
|minChildEndpoints|This parameter specifies the minimum number of endpoints that must be ‘online’ in the child profile in order for the parent profile to direct traffic to any of the endpoints in that child profile. It only applies to endpoints of type NestedEndpoints.|
|geoMapping|This parameter specifies the geographic regions that are mapped to this endpoint. It is only used if the endpoint is part of a profile that has routing type Geographic.|
