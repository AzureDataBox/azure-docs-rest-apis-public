# `<fully-qualifiediothubdomainname>.iothub.httpruntime.completedeviceboundnotification`

## `summary`
This method completes or rejects a cloud-to-device message. This method completes or rejects a cloud-to-device message. The Etag obtained when the message was received must be provided to resolve race conditions when completing, rejecting, or abandoning a message. A completed message is deleted from the device message queue, and a positive acknowledgment is sent to the application back-end if requested. A rejected message causes it to be deadlettered. To reject a message, include a query parameter called "reject". See https://docs.microsoft.com/azure/iot-hub/iot-hub-devguide-messaging for more information. Currently, the use of the Etag in the header does not comply with RFC 7232. A fix for this issue is currently on our backlog.


