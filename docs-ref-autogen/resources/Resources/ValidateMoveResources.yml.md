# `management.azure.com.resourcemanagement.resources.validatemoveresources`

## `summary`
Validates whether resources can be moved from one resource group to another resource group. This operation checks whether the specified resources can be moved to the target. The resources to move must be in the same source resource group. The target resource group may be in a different subscription. If validation succeeds, it returns HTTP response code 204 (no content). If validation fails, it returns HTTP response code 409 (Conflict) with an error message. Retrieve the URL in the Location header value to check the result of the long-running operation.


