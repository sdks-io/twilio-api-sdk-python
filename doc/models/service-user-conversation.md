
# Service User Conversation

*This model accepts additional fields of type Any.*

## Structure

`ServiceUserConversation`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `account_sid` | `str` | Optional | The unique ID of the [Account](https://www.twilio.com/docs/iam/api/account) responsible for this conversation.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^AC[0-9a-fA-F]{32}$` |
| `chat_service_sid` | `str` | Optional | The unique ID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) this conversation belongs to.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `conversation_sid` | `str` | Optional | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for this User Conversation.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^CH[0-9a-fA-F]{32}$` |
| `unread_messages_count` | `int` | Optional | The number of unread Messages in the Conversation for the Participant. |
| `last_read_message_index` | `int` | Optional | The index of the last Message in the Conversation that the Participant has read. |
| `participant_sid` | `str` | Optional | The unique ID of the [participant](https://www.twilio.com/docs/conversations/api/conversation-participant-resource) the user conversation belongs to.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^MB[0-9a-fA-F]{32}$` |
| `user_sid` | `str` | Optional | The unique string that identifies the [User resource](https://www.twilio.com/docs/conversations/api/user-resource).<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^US[0-9a-fA-F]{32}$` |
| `friendly_name` | `str` | Optional | The human-readable name of this conversation, limited to 256 characters. Optional. |
| `conversation_state` | [`ServiceUserConversationState`](../../doc/models/service-user-conversation-state.md) | Optional | The current state of this User Conversation. One of `inactive`, `active` or `closed`. |
| `timers` | `Any` | Optional | Timer date values representing state update for this conversation. |
| `attributes` | `str` | Optional | An optional string metadata field you can use to store any data you wish. The string value must contain structurally valid JSON if specified.  **Note** that if the attributes are not set "{}" will be returned. |
| `date_created` | `datetime` | Optional | The date that this conversation was created, given in ISO 8601 format. |
| `date_updated` | `datetime` | Optional | The date that this conversation was last updated, given in ISO 8601 format. |
| `created_by` | `str` | Optional | Identity of the creator of this Conversation. |
| `notification_level` | [`ServiceUserConversationNotificationLevel`](../../doc/models/service-user-conversation-notification-level.md) | Optional | The Notification Level of this User Conversation. One of `default` or `muted`. |
| `unique_name` | `str` | Optional | An application-defined string that uniquely identifies the Conversation resource. It can be used to address the resource in place of the resource's `conversation_sid` in the URL. |
| `url` | `str` | Optional | - |
| `links` | `Any` | Optional | Contains absolute URLs to access the [participant](https://www.twilio.com/docs/conversations/api/conversation-participant-resource) and [conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) of this conversation. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "account_sid": "account_sid6",
  "chat_service_sid": "chat_service_sid0",
  "conversation_sid": "conversation_sid4",
  "unread_messages_count": 154,
  "last_read_message_index": 200,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

