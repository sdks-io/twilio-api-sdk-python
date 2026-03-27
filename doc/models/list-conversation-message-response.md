
# List Conversation Message Response

*This model accepts additional fields of type Any.*

## Structure

`ListConversationMessageResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `messages` | [`List[ConversationMessage]`](../../doc/models/conversation-message.md) | Optional | - |
| `meta` | [`Meta`](../../doc/models/meta.md) | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "messages": [
    {
      "account_sid": "account_sid4",
      "conversation_sid": "conversation_sid4",
      "sid": "sid0",
      "index": 144,
      "author": "author8",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "account_sid": "account_sid4",
      "conversation_sid": "conversation_sid4",
      "sid": "sid0",
      "index": 144,
      "author": "author8",
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

