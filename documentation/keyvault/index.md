
---
ms.assetid: 16d4764e-3c9d-42b4-b749-bed20ca6b741
ms.title: Azure Key Vault REST API reference
ms.service: key-vault
author: BrucePerlerMS
ms.author: bruceper
ms.manager: mbaldwin
---

# Key Vault REST API Reference

Managing Key Vaults as well as keys, secrets, and certificates within Key Vaults can be accomplished through a REST interface.

Manage your Key Vaults using the following guidance:

- [Key Vault management](../../api-ref/keyvault/Vaults.json)

Managing within a Key Vault includes operations for creating, managing and executing cryptographic operations with keys, secrets and certificates within the Azure environment.

- [Key operations](key-operations.md)


- [Secret operations](secret-operations.md)


- [Certificate operations](certificate-operations.md)


For conceptual and detailed information, see - [About keys, secrets, and certificates](about-keys--secrets-and-certificates.md).

## Common tasks

Key Vaults


- [Manage key vaults](../../api-ref/keyvault/Vaults.json)




Keys


- [Create a key](../../api-ref/keyvault/CreateKey.json)


- [Get information about a key](../../api-ref/keyvault/GetKey.json)


- [Encrypt with a key](../../api-ref/keyvault/encrypt.json)



Secrets

- [Create a secret](../../api-ref/keyvault/SetSecret.json)


- [Get a secret](../../api-ref/keyvault/GetSecret.json)


Certificates


- [Create a certificate](../../api-ref/keyvault/CreateCertificate.json)


- [Import a certificate](../../api-ref/keyvault/ImportCertificate.json)


- [Update a certificate](../../api-ref/keyvault/UpdateCertificate.json)


- [Update a certificate policy](../../api-ref/keyvault/UpdateCertificatePolicy.json)

### See Also

- [About keys, secrets, and certificates](about-keys--secrets-and-certificates.md)
- [Authentication, requests and responses](authentication--requests-and-responses.md)
- [Key Vault versions](key-vault-versions.md)

