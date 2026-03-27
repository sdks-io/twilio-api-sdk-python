
# List Participant Conversation Response

*This model accepts additional fields of type Any.*

## Structure

`ListParticipantConversationResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `conversations` | [`List[ParticipantConversation]`](../../doc/models/participant-conversation.md) | Optional | - |
| `meta` | [`Meta`](../../doc/models/meta.md) | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "conversations": [
    {
      "account_sid": "account_sid6",
      "chat_service_sid": "chat_service_sid0",
      "participant_sid": "participant_sid8",
      "participant_user_sid": "participant_user_sid6",
      "participant_identity": "participant_identity2",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "meta": {
    "first_page_url": "first_page_url0",
    "key": "key2",
    "next_page_url": "next_page_url4",
    "page": 240,
    "page_size": 56,
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

