---
ms.assetid: 6153caf6-e970-4921-a55d-874784bc5e78
ms.title: Authorization REST API | Microsoft Docs
ms.service: azure-resource-manager
author: tfitzmac
ms.author: tomfitz
ms.manager: timlt
service_description: You use role-based access control to manage the actions users in your organization can take on resources. This set of operations enables you to define roles, assign roles to users or groups, and get information about permissions. 
---

# Authorization

You use role-based access control to manage the actions users in your organization can take on resources. This set of operations enables you to define roles, assign roles to users or groups, and get information about permissions.

For api-version, use 2015-07-01.

## REST Operation Groups

| Operation Group                                   | Description |
|---------------------------------------------------|-------------|
| [Classic Administrators](~/docs-ref-autogen/authorization/classicadministrators.json) | Provides information about administrators in a subscription. |
| [Permissions](~/docs-ref-autogen/authorization/permissions.json)                      | Provides operations to get the permissions assigned to resources and resource groups. |
| [Provider Operations Metadata](~/docs-ref-autogen/authorization/provideroperationsmetadata.json) | Provides operations for getting information about resource providers. |
| [Role Assignments](~/docs-ref-autogen/authorization/roleassignments.json)             | Provides operations for working with role assignments, such as assigning a role to a user or group. |
| [Role Definitions](~/docs-ref-autogen/authorization/roledefinitions.json)             | Provides operations for defining roles, such as what actions are permitted. |

## See Also

- [Add new users to Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-users-create-azure-portal)
- [Use role assignments to manage access to your Azure subscription resources](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure)