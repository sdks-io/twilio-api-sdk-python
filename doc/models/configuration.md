
# Configuration

*This model accepts additional fields of type Any.*

## Structure

`Configuration`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `account_sid` | `str` | Optional | The SID of the [Account](https://www.twilio.com/docs/iam/api/account) responsible for this configuration.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^AC[0-9a-fA-F]{32}$` |
| `default_chat_service_sid` | `str` | Optional | The SID of the default [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) used when creating a conversation.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `default_messaging_service_sid` | `str` | Optional | The SID of the default [Messaging Service](https://www.twilio.com/docs/messaging/api/service-resource) used when creating a conversation.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^MG[0-9a-fA-F]{32}$` |
| `default_inactive_timer` | `str` | Optional | Default ISO8601 duration when conversation will be switched to `inactive` state. Minimum value for this timer is 1 minute. |
| `default_closed_timer` | `str` | Optional | Default ISO8601 duration when conversation will be switched to `closed` state. Minimum value for this timer is 10 minutes. |
| `url` | `str` | Optional | An absolute API resource URL for this global configuration. |
| `links` | `Any` | Optional | Contains absolute API resource URLs to access the webhook and default service configurations. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "account_sid": "account_sid8",
  "default_chat_service_sid": "default_chat_service_sid2",
  "default_messaging_service_sid": "default_messaging_service_sid6",
  "default_inactive_timer": "default_inactive_timer2",
  "default_closed_timer": "default_closed_timer2",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

