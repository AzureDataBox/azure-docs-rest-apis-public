# `management.azure.com.recoveryservices-siterecovery.replicationrecoveryservicesproviders.delete`

## `summary`
Deletes provider from fabric. Note: Deleting provider for any fabric other than SingleHost is unsupported. To maintain backward compatibility for released clients the object "deleteRspInput" is used (if the object is empty we assume that it is old client and continue the old behavior). The operation to removes/delete(unregister) a recovery services provider from the vault


