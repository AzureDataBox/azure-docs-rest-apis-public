# `<fully-qualifiediothubdomainname>.iothub.httpruntime.abandondeviceboundnotification`

## `summary`
This method abandons a cloud-to-device message. This method abandons a cloud-to-device message. The Etag obtained when the message was received must be provided to resolve race conditions when completing, rejecting, or abandoning a message. A abandoned message is put back in the device message queue for re-delivery to the device. See https://docs.microsoft.com/azure/iot-hub/iot-hub-devguide-messaging for more information. Currently, the use of the Etag in the header does not comply with RFC 7232. A fix for this issue is currently on our backlog. 


