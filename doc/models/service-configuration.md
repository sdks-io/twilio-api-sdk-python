
# Service Configuration

*This model accepts additional fields of type Any.*

## Structure

`ServiceConfiguration`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Optional | The unique string that we created to identify the Service configuration resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `default_conversation_creator_role_sid` | `str` | Optional | The conversation-level role assigned to a conversation creator when they join a new conversation. See [Conversation Role](https://www.twilio.com/docs/conversations/api/role-resource) for more info about roles.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^RL[0-9a-fA-F]{32}$` |
| `default_conversation_role_sid` | `str` | Optional | The conversation-level role assigned to users when they are added to a conversation. See [Conversation Role](https://www.twilio.com/docs/conversations/api/role-resource) for more info about roles.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^RL[0-9a-fA-F]{32}$` |
| `default_chat_service_role_sid` | `str` | Optional | The service-level role assigned to users when they are added to the service. See [Conversation Role](https://www.twilio.com/docs/conversations/api/role-resource) for more info about roles.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^RL[0-9a-fA-F]{32}$` |
| `url` | `str` | Optional | An absolute API resource URL for this service configuration. |
| `links` | `Any` | Optional | Contains an absolute API resource URL to access the push notifications configuration of this service. |
| `reachability_enabled` | `bool` | Optional | Whether the [Reachability Indicator](https://www.twilio.com/docs/conversations/reachability) is enabled for this Conversations Service. The default is `false`. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "chat_service_sid": "chat_service_sid2",
  "default_conversation_creator_role_sid": "default_conversation_creator_role_sid2",
  "default_conversation_role_sid": "default_conversation_role_sid2",
  "default_chat_service_role_sid": "default_chat_service_role_sid2",
  "url": "url6",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

