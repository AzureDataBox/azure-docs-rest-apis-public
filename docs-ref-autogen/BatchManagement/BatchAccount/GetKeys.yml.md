# `management.azure.com.batchmanagement.batchaccount.getkeys`

## `summary`
Gets the account keys for the specified Batch account. This operation applies only to Batch accounts created with a poolAllocationMode of 'BatchService'. If the Batch account was created with a poolAllocationMode of 'UserSubscription', clients cannot use access to keys to authenticate, and must use Azure Active Directory instead. In this case, getting the keys will fail.


