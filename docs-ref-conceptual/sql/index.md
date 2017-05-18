---
ms.assetid: 709f9922-66f0-4315-ad60-4cac7beb4847
ms.title: Azure SQL Database REST API reference
ms.prod: azure
ms.service: sql-database
author:
ms.author: sstein
ms.manager: douge

---

# Azure SQL Database REST API

The Azure SQL Database REST API includes operations for managing Azure SQL Database servers, databases, elastic database pools, elastic databases, server firewall rules, and failover groups.

## REST Operation Groups

| Operation Group | Description |
|-----------------|-------------|
|[Databases](~/docs-ref-autogen/sql/Databases.json)| Create, get, update, and delete SQL databases, data warehouses, restore points, service tier advisors, and transparent data encryption configuration.|
|[Servers](~/docs-ref-autogen/sql/Servers.json)|Create, get, update, or list information about an Azure SQL server.|
|[Server Firewall Rules](~/docs-ref-autogen/sql/firewallrules.json)|Create, get, update, delete, or list firewall rules.|
|[Elastic Pools](~/docs-ref-autogen/sql/ElasticPools.json)|Create, get, update, or delete elastic pools.|
|[Recommended Elastic Pools](~/docs-ref-autogen/sql/RecommendedElasticPools.json)|Get and list information about Azure SQL recommended pools and Azure SQL databases inside pools.|
|[Database Replication Links](~/docs-ref-autogen/sql/databases%20-%20replicationlinks.json)| Get, list, delete, and failover a replication link.|
|[Failover Groups](~/docs-ref-autogen/sql/failovergroups.json)| Create, get, update, list, delete, and failover a failover group.| 


## See Also

- [Azure SQL Database](https://azure.microsoft.com/services/sql-database/)
- [Azure SQL Data Warehouse](https://azure.microsoft.com/services/sql-data-warehouse/)
- [Azure SQL Database Elastic Pool](https://azure.microsoft.com/documentation/articles/sql-database-elastic-pool/)