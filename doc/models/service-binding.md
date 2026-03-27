
# Service Binding

*This model accepts additional fields of type Any.*

## Structure

`ServiceBinding`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sid` | `str` | Optional | A 34 character string that uniquely identifies this resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^BS[0-9a-fA-F]{32}$` |
| `account_sid` | `str` | Optional | The unique ID of the [Account](https://www.twilio.com/docs/iam/api/account) responsible for this binding.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^AC[0-9a-fA-F]{32}$` |
| `chat_service_sid` | `str` | Optional | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Binding resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `credential_sid` | `str` | Optional | The SID of the [Credential](https://www.twilio.com/docs/conversations/api/credential-resource) for the binding. See [push notification configuration](https://www.twilio.com/docs/chat/push-notification-configuration) for more info.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^CR[0-9a-fA-F]{32}$` |
| `date_created` | `datetime` | Optional | The date that this resource was created. |
| `date_updated` | `datetime` | Optional | The date that this resource was last updated. |
| `endpoint` | `str` | Optional | The unique endpoint identifier for the Binding. The format of this value depends on the `binding_type`. |
| `identity` | `str` | Optional | The application-defined string that uniquely identifies the [Conversation User](https://www.twilio.com/docs/conversations/api/user-resource) within the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource). See [access tokens](https://www.twilio.com/docs/conversations/create-tokens) for more info. |
| `binding_type` | [`ServiceBindingBindingType`](../../doc/models/service-binding-binding-type.md) | Optional | The push technology to use for the Binding. Can be: `apn`, `gcm`, `fcm`, or `twilsock`.  See [push notification configuration](https://www.twilio.com/docs/chat/push-notification-configuration) for more info. |
| `message_types` | `List[str]` | Optional | The [Conversation message types](https://www.twilio.com/docs/chat/push-notification-configuration#push-types) the binding is subscribed to. |
| `url` | `str` | Optional | An absolute API resource URL for this binding. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "sid": "sid4",
  "account_sid": "account_sid8",
  "chat_service_sid": "chat_service_sid2",
  "credential_sid": "credential_sid2",
  "date_created": "2016-03-13T12:52:32.123Z",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

