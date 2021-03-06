---
title: "Triggers - Azure Cosmos DB REST API"
ms.date: "02/12/2016"
ms.service: "cosmos-db"
ms.topic: "reference"
ms.assetid: ede0c19d-6504-4355-9695-190c75e2bae4
caps.latest.revision: 6
author: "SnehaGunda"
ms.author: "sngun"
manager: "kfile"
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
# Triggers
[Azure Cosmos DB](/azure/cosmos-db/introduction) is a globally distributed multi-model database that supports the document, graph, and key-value data models. The content in this section is for managing trigger [resources](/azure/cosmos-db/sql-api-resources) using the [SQL API](/azure/cosmos-db/sql-api-introduction) via REST.  

Triggers are pieces of application logic that can be executed before (pre-triggers) and after (post-triggers) creation, deletion, and replacement of a document. Triggers are written in JavaScript. Both pre and post triggers do no take parameters. Like stored procedures, triggers live within the confines of a collection, thus confining the application logic to the collection.  
  
Similar to stored procedures, the triggers resource has a fixed schema. The body property contains the application logic. The following example illustrates the JSON construct of a trigger.  
  
```  
{  
"id":"PostTrigger-UpdateMetaAll",  
"body": "  
function updateMetadata() {  
        var context = getContext();  
        var collection = context.getCollection();  
        var response = context.getResponse();  
        var createdDocument = response.getBody();  
  
        // query for metadata document  
        var filterQuery = 'SELECT * FROM root r WHERE r.id = "_metadata"';  
        var accept = collection.queryDocuments(collection.getSelfLink(), filterQuery,  
            updateMetadataCallback);  
        if(!accept) throw "Unable to update metadata, abort";  
  
        function updateMetadataCallback(err, documents, responseOptions) {  
            if(err) throw new Error("Error" + err.message);  
                     if(documents.length != 1) throw 'Unable to find metadata document';  
                     var metadataDocument = documents[0];  
  
                     // update metadata  
                     metadataDocument.createdDocuments += 1;  
                     metadataDocument.createdNames += " " + createdDocument.id;  
                     var accept = collection.replaceDocument(metadataDocument._self,  
                           metadataDocument, function(err, docReplaced) {  
                                  if(err) throw "Unable to update metadata, abort";  
                           });  
                     if(!accept) throw "Unable to update metadata, abort";  
                     return;                      
        }  
}  
",  
"_rid":"hLEEAI1YjgcBAAAAAAAAgA==",  
"_ts":1408058682,  
"_self":"dbs\/hLEEAA==\/colls\/hLEEAI1Yjgc=\/udfs\/hLEEAI1YjgcBAAAAAAAAgA==\/",  
"_etag":"00004100-0000-0000-0000-53ed453a0000"  
}  
  
```  
  
|Property|Description|  
|--------------|-----------------|  
|**id**|Required. It is a user settable property. It is the unique name used to identify the trigger. The **ID** must not exceed 255 characters.|  
|**body**|Required. It is a user settable property. It is the body of the trigger.|  
|**triggerOperation**|Required. It is the type of operation that invokes the trigger. The acceptable values are: **All**, **Insert**, **Replace** and **Delete.**|  
|**triggerType**|Required. This specifies when the trigger is fired. The acceptable values are: **Pre** and **Post**. **Pre** triggers fire before an operation while **Post** triggers after an operation.|  
|**_rid**|It is a system generated property. The resource ID (**_rid**) is a unique identifier that is also hierarchical per the resource stack on the resource model. It is used internally for placement and navigation of the trigger resource.|  
|**_ts**|It is a system generated property. It specifies the last updated timestamp of the resource. The value is a timestamp.|  
|**_self**|It is a system generated property. It is the uniquely addressable URI for the resource.|  
|**_etag**|It is a system generated property that specifies the resource etag required for optimistic concurrency control.|  
  
## Tasks  
You can do the following with triggers:  
  
-   [Create a Trigger](create-a-trigger.md)   
-   [Replace a Trigger](replace-a-trigger.md)  
-   [List Triggers](list-triggers.md)  
-   [Delete a Trigger](delete-a-trigger.md)  
  
For information on how UDFs work including invoking a trigger, see [Azure Cosmos DB programming: Stored procedures, triggers, and UDFs](/azure/cosmos-db/programming/).  
  
## See Also  
* [Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/introduction) 
* [Azure Cosmos DB SQL API](https://docs.microsoft.com/azure/cosmos-db/sql-api-introduction)   
* [Azure Cosmos DB SQL API SDKs](https://docs.microsoft.com/en-us/azure/cosmos-db/sql-api-sdk-dotnet)    
* [REST from .NET Sample](https://github.com/Azure/azure-documentdb-dotnet/tree/master/samples/rest-from-.net)  
  

