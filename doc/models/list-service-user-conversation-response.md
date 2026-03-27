
# List Service User Conversation Response

*This model accepts additional fields of type Any.*

## Structure

`ListServiceUserConversationResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `conversations` | [`List[ServiceUserConversation]`](../../doc/models/service-user-conversation.md) | Optional | - |
| `meta` | [`Meta`](../../doc/models/meta.md) | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "conversations": [
    {
      "account_sid": "account_sid6",
      "chat_service_sid": "chat_service_sid0",
      "conversation_sid": "conversation_sid6",
      "unread_messages_count": 76,
      "last_read_message_index": 174,
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "account_sid": "account_sid6",
      "chat_service_sid": "chat_service_sid0",
      "conversation_sid": "conversation_sid6",
      "unread_messages_count": 76,
      "last_read_message_index": 174,
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "account_sid": "account_sid6",
      "chat_service_sid": "chat_service_sid0",
      "conversation_sid": "conversation_sid6",
      "unread_messages_count": 76,
      "last_read_message_index": 174,
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

