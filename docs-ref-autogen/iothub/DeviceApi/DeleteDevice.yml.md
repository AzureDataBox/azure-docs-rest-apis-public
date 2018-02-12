# `<fully-qualifiediothubdomainname>.iothub.deviceapi.deletedevice`

## `summary`
Delete the identity of a device from the identity registry of an IoT hub. Delete the identity of a device from the identity registry of an IoT hub. This request requires the If-Match header. The client may specify the ETag for the device identity on the request in order to compare to the ETag maintained by the service for the purpose of optimistic concurrency. The delete operation is performed only if the ETag sent by the client matches the value maintained by the server, indicating that the device identity has not been modified since it was retrieved by the client. To force an unconditional delete, set If-Match to the wildcard character (*).


