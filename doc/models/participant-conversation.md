
# Participant Conversation

*This model accepts additional fields of type Any.*

## Structure

`ParticipantConversation`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `account_sid` | `str` | Optional | The unique ID of the [Account](https://www.twilio.com/docs/iam/api/account) responsible for this conversation.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^AC[0-9a-fA-F]{32}$` |
| `chat_service_sid` | `str` | Optional | The unique ID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) this conversation belongs to.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `participant_sid` | `str` | Optional | The unique ID of the [Participant](https://www.twilio.com/docs/conversations/api/conversation-participant-resource).<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^MB[0-9a-fA-F]{32}$` |
| `participant_user_sid` | `str` | Optional | The unique string that identifies the conversation participant as [Conversation User](https://www.twilio.com/docs/conversations/api/user-resource).<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^US[0-9a-fA-F]{32}$` |
| `participant_identity` | `str` | Optional | A unique string identifier for the conversation participant as [Conversation User](https://www.twilio.com/docs/conversations/api/user-resource). This parameter is non-null if (and only if) the participant is using the Conversations SDK to communicate. Limited to 256 characters. |
| `participant_messaging_binding` | `Any` | Optional | Information about how this participant exchanges messages with the conversation. A JSON parameter consisting of type and address fields of the participant. |
| `conversation_sid` | `str` | Optional | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) this Participant belongs to.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^CH[0-9a-fA-F]{32}$` |
| `conversation_unique_name` | `str` | Optional | An application-defined string that uniquely identifies the Conversation resource. |
| `conversation_friendly_name` | `str` | Optional | The human-readable name of this conversation, limited to 256 characters. Optional. |
| `conversation_attributes` | `str` | Optional | An optional string metadata field you can use to store any data you wish. The string value must contain structurally valid JSON if specified.  **Note** that if the attributes are not set "{}" will be returned. |
| `conversation_date_created` | `datetime` | Optional | The date that this conversation was created, given in ISO 8601 format. |
| `conversation_date_updated` | `datetime` | Optional | The date that this conversation was last updated, given in ISO 8601 format. |
| `conversation_created_by` | `str` | Optional | Identity of the creator of this Conversation. |
| `conversation_state` | [`ParticipantConversationState`](../../doc/models/participant-conversation-state.md) | Optional | The current state of this User Conversation. One of `inactive`, `active` or `closed`. |
| `conversation_timers` | `Any` | Optional | Timer date values representing state update for this conversation. |
| `links` | `Any` | Optional | Contains absolute URLs to access the [participant](https://www.twilio.com/docs/conversations/api/conversation-participant-resource) and [conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) of this conversation. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "account_sid": "account_sid4",
  "chat_service_sid": "chat_service_sid8",
  "participant_sid": "participant_sid6",
  "participant_user_sid": "participant_user_sid4",
  "participant_identity": "participant_identity0",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

