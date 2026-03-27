
# List Service Conversation Participant Response

*This model accepts additional fields of type Any.*

## Structure

`ListServiceConversationParticipantResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `participants` | [`List[ServiceConversationParticipant]`](../../doc/models/service-conversation-participant.md) | Optional | - |
| `meta` | [`Meta`](../../doc/models/meta.md) | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "participants": [
    {
      "account_sid": "account_sid0",
      "chat_service_sid": "chat_service_sid4",
      "conversation_sid": "conversation_sid0",
      "sid": "sid6",
      "identity": "identity8",
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

