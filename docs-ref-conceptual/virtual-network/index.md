---
ms.title: Virtual Network REST APIs
ms.date: 03/15/2017
ms.service: virtual-network
ms.topic: reference
ms.devlang: rest
author: anavinahar 
ms.author: annahar 
ms.manager: narayan
---

# Virtual Networks REST API

## Virtual Networks

A virtual network represents a computer network in which networking objects can be created. The virtual network reserves an address space and defines subnets in this address space. The DHCP options defined on a virtual network by default get applied to the NICs connected to this network.  

| Operation | REST Verb | Description | 
|---------|---------|-----------|
| [Create or update a virtual network](~/docs-ref-autogen/virtual-network/virtualnetworks.json#VirtualNetworks_CreateOrUpdate)   |  PUT | Creates or updates a virtual network. |  
| [List virtual networks within a resource group](~/docs-ref-autogen/virtual-network/virtualnetworks.json#VirtualNetworks_List)         |  GET | Gets all virtual networks in a resource group. |  
| [List virtual networks within a subscription](~/docs-ref-autogen/virtual-network/virtualnetworks.json#VirtualNetworks_List)         |  GET | Gets all virtual networks in a subscription. |  
| [Get information about a virtual network](~/docs-ref-autogen/virtual-network/virtualnetworks.json#VirtualNetworks_List)       |  GET | Gets a virtual network. |  
| [Delete a virtual network](~/docs-ref-autogen/virtual-network/virtualnetworks.json#VirtualNetworks_Delete)      |  DELETE | Deletes a virtual network. |  
| [Check private IP address availability in a virtual network](~/docs-ref-autogen/virtual-network/virtualnetworks.json#VirtualNetworks_CheckIPAddressAvailability) |  GET | Check if a private IP address is available in a virtual network. |  
| [Create or update a virtual network peering](~/docs-ref-autogen/virtual-network/virtualnetworkpeerings.json#VirtualNetworkPeerings_CreateOrUpdate)|  PUT | Creates or updates a virtual network peering. |  
| [List virtual network peerings within a virtual network](~/docs-ref-autogen/virtual-network/virtualnetworkpeerings.json#VirtualNetworkPeerings_List)|  GET | Gets all virtual network peerings in a virtual network. |  
| [Get information about a virtual network peering](~/docs-ref-autogen/virtual-network/virtualnetworkpeerings.json#VirtualNetworkPeerings_Get)|  GET | Gets a virtual network peering. |  
| [Delete a virtual network peering](~/docs-ref-autogen/virtual-network/virtualnetworkpeerings.json#VirtualNetworkPeerings_Delete)|  DELETE | Deletes a virtual network peering. |  

## Subnets

Subnets represent network segments within the IP space defined by the virtual network.  
  
Subnets are child resources of a virtual network. Subnets have names unique within a VNET and they can be addressed via URIs. Subnets can be added and deleted by updating VNET or via PUT/DELETE against individual subnets.  

| Operation | REST Verb | Description | 
|---------|---------|-----------|
| [Create or update a subnet](~/docs-ref-autogen/virtual-network/subnets.json#Subnets_CreateOrUpdate)       |  PUT | Creates or updates a subnet. |  
| [Delete a subnet](~/docs-ref-autogen/virtual-network/subnets.json#Subnets_Delete)            |  DELETE | Deletes a subnet. |  
| [Get information about a subnet](~/docs-ref-autogen/virtual-network/subnets.json#Subnets_Get)             |  GET | Gets a subnet. |  
| [List subnets within a virtual network](~/docs-ref-autogen/virtual-network/subnets.json#Subnets_List)    |  GET | Gets all subnets in a virtual network. |  

#@ Network Interface Cards

Network interface cards are virtual network cards that form the link between virtual machines and the virtual network. Each VM has at least 1 network interface card. Multiple subnets can be bound to the same network interface card and can have 1 or more IP addresses bound to it. Network interface cards must be associated with a public IP address to be accessible over the Internet.  

This table lists the operations included in the Topology REST API.  
  
| Operation | REST Verb | Description | 
|---------|---------|-----------|
| [Create or update a network interface card](~/docs-ref-autogen/virtual-network/networkinterfaces.json#NetworkInterfaces_CreateOrUpdate)   |  PUT | Creates or updates a network interface card. |  
| [Delete a network interface card](~/docs-ref-autogen/virtual-network/networkinterfaces.json#NetworkInterfaces_Delete)  |  DELETE | Deletes a network interface card. |  
| [Get information about a network interface card](~/docs-ref-autogen/virtual-network/networkinterfaces.json#NetworkInterfaces_Get)    |  GET | Gets a network interface card. |  
| [List network interface cards within a resource group](~/docs-ref-autogen/virtual-network/networkinterfaces.json#NetworkInterfaces_List)  |  GET | Gets all network interface cards in a resource group. |  
| [List network interface cards within a subscription](~/docs-ref-autogen/virtual-network/networkinterfaces.json#NetworkInterfaces_ListAll) |  GET | Gets all network interface cards within a subscription. |  
| [Get effective network security group](~/docs-ref-autogen/virtual-network/networkinterfaces.json#NetworkInterfaces_ListEffectiveNetworkSecurityGroups)  |  GET | Gets the effective network security group for a network interface. |  
| [Get effective route table](~/docs-ref-autogen/virtual-network/networkinterfaces.json#NetworkInterfaces_GetEffectiveRouteTable)  |  GET | Gets the effective route table for a network interface |  

## Route Tables

Route table resource is associated with a subnet. The route table resource enables addition of user defined routes.  

| Operation | REST Verb | Description | 
|---------|---------|-----------|
| [Create or update a route table](~/docs-ref-autogen/virtual-network/routetables.json#RouteTables_CreateOrUpdate)   |  PUT | Creates or updates a route table. |  
| [Delete a route table](~/docs-ref-autogen/virtual-network/routetables.json#RouteTables_Delete)        |  DELETE | Deletes a route table. |  
| [Get information about a route table](~/docs-ref-autogen/virtual-network/routetables.json#RouteTables_Get)           |  GET | Gets a route table. |  
| [List route tables within a resource group](~/docs-ref-autogen/virtual-network/routetables.json#RouteTables_ListAll)     |  GET | Gets all route tables in a resource group. | 

## Routes

Route resource describes the packet forwarding rule for a given IP address or a range of IP addresses.  A route resource is associated with a route table.  

| Operation | REST Verb | Description | 
|---------|---------|-----------|
| [Create or update a route](~/docs-ref-autogen/virtual-network/routes.json#Routes_CreateOrUpdate)     |  PUT | Creates or updates a route. |  
| [Delete a route](~/docs-ref-autogen/virtual-network/routes.json#Routes_Delete)          |  DELETE | Deletes a route. |  
| [Get information about a route](~/docs-ref-autogen/virtual-network/routes.json#Routes_Get)             |  GET | Gets a route. |  
| [List routes within a route table](~/docs-ref-autogen/virtual-network/routes.json#Routes_List)    |  GET | Gets all routes in a route table. |  

## Public IP Addresses

Public IP addresses can be used to acquire a static or dynamic public IP address. Public IP addresses can be used to publish your applications for access over the Internet. A static public IP address gets its value when the public IP address resource is created, and it keeps its value even if it is not associated with a running VM. Static public IP addresses are guaranteed to retain the same IP when that public IP address is transferred across load balancers or network interface cards. A dynamic public IP address gets its value when it is associated with a VM, and it loses its value in certain scenarios. For example, a dynamic public IP address will change its value when it is disassociated from one VM and assigned to another VM.  
  
Public IP addresses can be assigned to a load balancer, or directly to a network interface of a VM. Associating a public IP address directly with the network interface of a VM makes it an instance-level public IP address. This means that all ports can be used for communication, except if traffic is controlled via security groups. When a public IP address is assigned to a load balancer, traffic flow to and through the public IP address is defined by the rules of the load balancer. Security groups to control traffic can be used in this scenario as well  

| Operation | REST Verb | Description | 
|---------|---------|-----------|
| [Create or update a public IP address ](~/docs-ref-autogen/virtual-network/publicipaddresses.json#PublicIPAddresses_CreateOrUpdate)  |  PUT | Creates or updates a public IP address. |  
| [Delete a public IP address ](~/docs-ref-autogen/virtual-network/publicipaddresses.json#PublicIPAddresses_Delete)      |  DELETE | Deletes a public IP address. |  
| [Get information about a public IP address ](~/docs-ref-autogen/virtual-network/publicipaddresses.json#PublicIPAddresses_Get)         |  GET | Gets a public IP address. |  
| [List public IP addresses within a resource group ](~/docs-ref-autogen/virtual-network/publicipaddresses.json#PublicIPAddresses_List)     |  GET | Gets all public IP address in a resource group. |  
| [List public IP addresses within a subscription ](~/docs-ref-autogen/virtual-network/publicipaddresses.json#PublicIPAddresses_ListAll)     |  GET | Gets all public IP addresses in a subscription. |  

## Network Security Groups

A network security group (NSG) resource contains a list of network security rules. NSGs enable inbound or outbound traffic to be enabled or denied.  
  
NSGs are created with a set of default network security rules which are designed to enable all communications from and within a virtual network, but deny external access to same.  
  
NSGs can be assigned to subnets or individual NICs. Where NSGs are assigned to both a subnet and a NIC, the combination of both NSGs applies to that NIC.  

| Operation | REST Verb | Description | 
|---------|---------|-----------|
| [Create or update a network security group](~/docs-ref-autogen/virtual-network/networksecuritygroups.json#NetworkSecurityGroups_CreateOrUpdate)     |  PUT | Creates or updates a network security group. |  
| [Delete a network security group](~/docs-ref-autogen/virtual-network/networksecuritygroups.json#NetworkSecurityGroups_Delete)    |  DELETE | Deletes a network security group. |  
| [Get information about a network security group](~/docs-ref-autogen/virtual-network/networksecuritygroups.json#NetworkSecurityGroups_Get)    |  GET | Gets a network security group. |  
| [List network security groups within a resource group](~/docs-ref-autogen/virtual-network/networksecuritygroups.json#NetworkSecurityGroups_List)|  GET | Gets all network security groups within a resource group. |  
| [Get effective network security group](~/docs-ref-autogen/virtual-network/networksecuritygroups.json#NetworkSecurityGroups_ListAll) |  GET | Gets the effective network security group for a network interface card. |  

## Network Security Rules

Network security rules define a pattern of traffic to be enabled or denied. Network security rules are contained within a Network Security Group (NSG). NSGs can be applied at the subnet or NIC level.  
  
Default network security rules are created to protect your virtual network by default. It is not possible to edit or delete a default network security rule, but they can be overridden by creating a network security rule with a lower priority. Default network security rules have priorities of 65000 and greater. To override a default network security rule, create a network security rule with a priority of less than 65000.  

| Operation | REST Verb | Description | 
|---------|---------|-----------|
| [Create or update a network security group](~/docs-ref-autogen/virtual-network/securityrules.json#SecurityRules_CreateOrUpdate) |  PUT | Creates or updates a network security rule. |  
| [Delete a network security rule](~/docs-ref-autogen/virtual-network/securityrules.json#SecurityRules_Delete)       |  DELETE | Deletes a network security rule. |  
| [Get information about a default network security rule ](~/docs-ref-autogen/virtual-network/securityrules.json#SecurityRules_Get)       |  GET | Gets a default network security rule. |  
| [Get information about a network security rule ](~/docs-ref-autogen/virtual-network/securityrules.json#SecurityRules_Get)      |  GET | Gets a network security rule. | 
| [List networks security rules within a network security group](~/docs-ref-autogen/virtual-network/securityrules.json#SecurityRules_List)|  GET | Gets all network security rules in a network security group. |  

## Supporting tasks

A number of actions are possible to support your management of network resources.  
  
| Operation | REST Verb | Description | 
|---------|---------|-----------|
| [Check DNS name availability](~/docs-ref-autogen/virtual-network/checkdnsnameavailability.json)       |  GET | Checks if the DNS name is available . |  
| [Check subscription usages](~/docs-ref-autogen/virtual-network/usages.json)           |  GET | Returns the subscription usage for a region. |  