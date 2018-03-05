---
ms.assetid: 16d4764e-3c9d-42b4-b749-bed20ca6b741
ms.title: Azure Key Vault REST API reference | Microsoft Docs
ms.service: key-vault
author: BrucePerlerMS
ms.author: bruceper
ms.manager: mbaldwin
ms.date: 06/21/2017
---

# Azure Key Vault REST API reference

Managing your key vaults as well as the keys, secrets, and certificates within your key vaults can be accomplished through a REST interface.

Manage your key vaults using the following set of operations.

- [Manage key vaults](xref:management.azure.com.keyvault.vaults)

Managing within a Key Vault includes operations for creating, managing and executing cryptographic operations with keys, secrets and certificates within the Azure environment.

- [Key operations](key-operations.md)
- [Secret operations](secret-operations.md)
- [Certificate operations](certificate-operations.md)

For conceptual and detailed information, see - [About keys, secrets, and certificates](about-keys--secrets-and-certificates.md).

## Common tasks

### Key vaults

- [Create or update a key vault](../../docs-ref-autogen/keyvault/Vaults.yml#Vaults_CreateOrUpdate)
- [Deletes a key vault](../../docs-ref-autogen/keyvault/Vaults.yml#Vaults_Delete)
- [Gets info about a key vault](../../docs-ref-autogen/keyvault/Vaults.yml#Vaults_Get)

### Keys

- [Create a key](xref:keyvault.createkey)
- [Get information about a key](xref:keyvault.getkey)
- [Encrypt with a key](xref:keyvault.encrypt)
- [Recover deleted key](xref:keyvault.recoverdeletedkey)

### Secrets

- [Create a secret](xref:keyvault.setsecret)
- [Get a secret](xref:keyvault.getsecret)
- [Recover deleted secret](xref:keyvault.recoverdeletedsecret)

### Certificates

- [Create a certificate](xref:keyvault.createcertificate)
- [Import a certificate](xref:keyvault.importcertificate)
- [Update a certificate](xref:keyvault.updatecertificate)
- [Update a certificate policy](xref:keyvault.updatecertificatepolicy)
- [Recover deleted certificate](xref:keyvault.recoverdeletedcertificate)

### Storage accounts

- [Set a storage account](xref:keyvault.setstorageaccount)
- [Get a storage account](xref:keyvault.getstorageaccount)
- [Delete a storage account](xref:keyvault.deletestorageaccount)

### See also

- [About keys, secrets, and certificates](about-keys--secrets-and-certificates.md)
- [Authentication, requests and responses](authentication--requests-and-responses.md)
- [Key Vault Developer's Guide](/azure/key-vault/key-vault-developers-guide)
- [Key Vault versions](key-vault-versions.md)

