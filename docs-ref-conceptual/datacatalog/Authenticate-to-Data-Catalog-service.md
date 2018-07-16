---
title: "Authenticate to Data Catalog service"
ms.custom: na
ms.date: 2017-11-09
ms.prod: azure
ms.reviewer: na
ms.service: data-catalog
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: reference
ms.assetid: 0dae6844-5732-4374-8c43-c62e3071df44
caps.latest.revision: 16
author: spelluru
manager: jhubbard
translation.priority.mt: 
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - pt-br
  - ru-ru
  - zh-cn
  - zh-tw
---
# Authenticate to Data Catalog service
The Data Catalog REST API is a REST-based API that provides programmatic access to Data Catalog resources to register, annotate, and search data assets programmatically.  
### In this article  
- [Introduction to authentication in Data Catalog](#intro)  
- [Azure app client ID](#clientID)  

<a name="intro"/><br/>## Introduction to authentication in Data Catalog<br/>Data Catalog apps are integrated with <strong>Azure Active Directory</strong> (Azure AD) to provide secure sign-in and authorization for your app. To integrate a Data Catalog app with Azure AD, you register the details about your application with Azure AD by using the Azure portal. When you register an app in Azure Active Directory, the application outsources authentication to Azure AD. App registration involves telling Azure AD about your application including the URL where it is located, the URL to send replies after authentication, and the URI to identify your application. When you register a client app or web app in Azure AD, you give your app access to the Data Catalog REST API.<br/>
A Data Catalog app uses a <strong>Client ID</strong> to identify itself to Azure AD. See <a href="#clientID" data-raw-source="[Azure app client ID](#clientID)">Azure app client ID</a>.<br/>
To learn how to register and authenticate a Data Catalog app:<br/>
- <strong>Data Catalog client app</strong>: See <a href="Register-a-client-app.md" data-raw-source="[Register a client app](Register-a-client-app.md)">Register a client app</a> and <a href="Authenticate-a-client-app.md" data-raw-source="[Authenticate a Data Catalog client app](Authenticate-a-client-app.md)">Authenticate a Data Catalog client app</a>.<br/>
- To learn how to use Azure authentication on different platforms: The <a href="https://msdn.microsoft.com/library/azure/dn151135.aspx" data-raw-source="[Azure Authentication Libraries](https://msdn.microsoft.com/library/azure/dn151135.aspx)">Azure Authentication Libraries</a> are available on different platforms to help developers easily authenticate users to cloud or o-premises Active Directory (AD) to obtain access tokens for securing API calls. This topic contains a roadmap to the authentication libraries available on different platforms and to helpful resources for each, including source code and samples.<br/>
<a name="clientID"/><br/>## Azure app client ID<br/>An Azure app has a <strong>Client ID</strong> that is used by the application to identify themselves to the users that they are requesting permissions from. You use a <strong>Client ID</strong> to get an authentication token. To get an Azure <strong>Client ID</strong>, see <a href="Register-a-client-app.md#clientID" data-raw-source="[How to get a client app ID](Register-a-client-app.md#clientID)">How to get a client app ID</a>.<br/>
For a complete sample of how to use an Azure <strong>Client ID</strong> to authenticate a client app, see <a href="Authenticate-a-client-app.md" data-raw-source="[Authenticate a client app](Authenticate-a-client-app.md)">Authenticate a client app</a>.<br/>  
