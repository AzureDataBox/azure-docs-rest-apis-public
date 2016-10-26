# Azure REST API Reference

Welcome to the Azure REST API Reference.

Representational State Transfer (REST) APIs are service endpoints that support sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources. The sections below will walk you through the basics of [REST API request and response components](#components-of-a-rest-api-requestresponse), how to [authenticate your client application](#authenticate-your-client-application) before making REST requests, how to [create a REST request](#create-the-request), and [handling the REST response](#process-the-response).

## Components of a REST API request/response

A REST API request/response pair can be separated into 5 components:

- The **URI**, which consists of the following: `{URI-scheme} :// {URI-host} / {resource-path} ? {query-string}`
    - URI scheme: indicates the protocol used to transmit the request. For example, `http` or `https`.  
    - URI host: the domain name or IP address of the server where the REST service endpoint is hosted.  
    - Resource path: specifies the resource or resource collection, which may include multiple segments used by the service in determining the selection of those resources. For example: `applications/f586155a-cbb2-4b13-9b56-16de60101cb9/owners` could be used to query the list of owners of a specific application within the applications collection.
    - Query string (optional): used to provide additional simple parameters, such as the API version, selection criteria, etc.
- HTTP **request message header** fields
    - A required [HTTP method](http://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html) (also known as an operation or verb). Azure REST APIs support GET, HEAD, PUT, POST, and PATCH methods.
    - Optional additional header fields as required by the specified URI and HTTP method. For example, an Authorization header that provides a bearer token containing client authorization information for the request.
- Optional HTTP **request message body** fields, to support the URI and HTTP operation. For example, POST operations contain MIME-encoded objects passed as complex parameters. The MIME encoding type for the body should be provided in the `Content-type` request header as well, for POST/PUT operations. Note that some services require you to use a specific MIME type, such as `application/json`.  
- HTTP **response message header** fields
    - An [HTTP status code](http://www.w3.org/Protocols/HTTP/HTRESP.html), ranging from 2xx success codes to 4xx/5xx error codes. Alternatively, a service-defined status code may be returned, as indicated in the API documentation. 
- Optional HTTP **response message body** fields
    - MIME-encoded response objects may be returned in the HTTP response body, such as a response from a GET method that is returning data. Typically these will be returned in a structured format as JSON or XML, as indicated by the `Content-type` response header. For example, when requesting an access token from Azure AD, it will be returned in the response body as the `access_token` element, one of several name/value paired objects in a data collection. In this example, a response header of `Content-Type: application/json` will also be included.

> For almost all Azure service REST APIs, there is a corresponding client SDK library which handles much of the client code for you. See:  
> [Azure .NET SDK](https://docs.microsoft.com/en-us/dotnet/api)  
> [Azure Java SDK](https://docs.microsoft.com/en-us/java/api)  
> [Azure CLI 2.0 SDK](https://docs.microsoft.com/en-us/cli/azure)  

## Authenticate your client application

Many Azure services require your client code to authenticate with valid credentials before you can call the service API, which also allows the service to perform any required authorization. Azure Resource Manager REST APIs require authentication, therefore client applications **must** authenticate with Azure Active Directory (AD), and provide proof of the authentication/authorization by passing the resulting OAuth2 bearer token in the HTTP Authorization header of subsequent REST API requests. 

Before you begin writing your client's request code, follow the instructions below to first register your [client application](https://azure.microsoft.com/documentation/articles/active-directory-dev-glossary/#client-application) with Azure AD. If you've already registered a client application, you can skip to the [Create the request](#create-the-request) section. 

1. Azure AD and the OAuth2 Authorization Framework support 2 types of clients. Before you register your application, decide which is the most appropriate for your scenario:  
    - [confidential/web](https://azure.microsoft.com/documentation/articles/active-directory-dev-glossary/#web-client) clients can access resources under either their own identity (as a service/daemon), or a signed-in end-user (an interactive resource owner) identity.  
    - [public/native](https://azure.microsoft.com/documentation/articles/active-directory-dev-glossary/#native-client) clients (installed on a device)  can only access resources under a signed-in end-user's identity. 
2. Next, refer to one of the articles below, and register your application as either a web or native client :
    - To use an Azure Resource Manager API, see [Use portal to create Active Directory application and service principal that can access resources](https://azure.microsoft.com/documentation/articles/resource-group-create-service-principal-portal/) for step-by-step registration instructions. This article will not only show you how to register the client application with Azure AD, it will also walk you through the steps required by Azure Resource Manager to properly configure it's Role Based Access Control (RBAC) settings for authorizing the client.
    - For all other Azure REST APIs that require an Authorization header, see [Authorize access to web applications using OAuth 2.0 and Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-protocols-oauth-code/)


## Create the request

Before you can call an Azure REST API that requires client authentication, you must authenticate your client application with Azure AD. Azure AD exposes several service endpoints to facilitate application integration, but the 2 you will be interested in using are the /authorize and /token endpoints. How you use those endpoints will be dependent on your application's registration, and the type of [authorization grant flow](https://azure.microsoft.com/documentation/articles/active-directory-dev-glossary/#authorization-grant) you need to support your application at runtime.

For the purposes of this article, we will assume your client will be using one of the following authorization grant flows:

- authorization code grant
- client credentials grant

2. Modify your client application to pass a bearer token in an Authorization header
    - Authenticate with Azure AD
    - Construct an HTTP Authorization header when calling ARM


> [!NOTE] If you prefer to use client libraries to manage token acquisition instead of using the Azure AD REST endpoints. For more details, including reference documentation, library downloads, and sample code, please see [Azure Active Directory Authentication Libraries](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/).

3. Call the REST API

## Process the response
In the example provided above, we used the /subscriptions endpoint to retrieve the list of subscriptions for our sample client application.

## Related content
- [Integrating applications with Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-integrating-applications/)
- For testing HTTP requests/responses, checkout [Fiddler](http://www.telerik.com/fiddler)

Token inspection

