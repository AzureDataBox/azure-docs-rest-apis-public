---
ms.assetid: 45dc6cfc-8ce9-4728-b2a2-66c9cbda3a3d
title: Key operations | Microsoft Docs
ms.service: key-vault
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.date: 04/28/2017
---
# Key operations

The Azure Key Vault REST API supports the following operations for key objects.

- [Create a key](../../docs-ref-autogen/keyvault/CreateKey.json)
- [Update a key](../../docs-ref-autogen/keyvault/UpdateKey.json)
- [Delete a key](../../docs-ref-autogen/keyvault/DeleteKey.json)
- [Get information about a key](../../docs-ref-autogen/keyvault/GetKey.json)
- [Get the keys in a vault](../../docs-ref-autogen/keyvault/GetKeys.json)
- [Get the versions of a key](../../docs-ref-autogen/keyvault/GetKeyVersions.json)
- [Import a key into a vault](../../docs-ref-autogen/keyvault/ImportKey.json)
- [Backup a key](../../docs-ref-autogen/keyvault/BackupKey.json)
- [Restore a key](../../docs-ref-autogen/keyvault/RestoreKey.json)

## Cryptographic operations

- [Encrypt with a key](../../docs-ref-autogen/keyvault/encrypt.json)
- [Decrypt with a key](../../docs-ref-autogen/keyvault/decrypt.json)
- [Sign with a key](../../docs-ref-autogen/keyvault/sign.json)
- [Verify with a key](../../docs-ref-autogen/keyvault/verify.json)
- [Wrap a key](../../docs-ref-autogen/keyvault/wrapKey.json)
- [Unwrap a key](../../docs-ref-autogen/keyvault/unwrapKey.json)

## Soft-delete operations

- [Get deleted key](../../docs-ref-autogen/keyvault/GetDeletedKey.json)
- [Get deleted keys](../../docs-ref-autogen/keyvault/GetDeletedKeys.json)
- [Purge deleted key](../../docs-ref-autogen/keyvault/PurgeDeletedKey.json)
- [Recover deleted key](../../docs-ref-autogen/keyvault/RecoverDeletedKey.json)

## See Also

- [Common parameters and headers](common-parameters-and-headers.md)
- [About keys, secrets, and certificates](about-keys--secrets-and-certificates.md)
