
# List Service Conversation Scoped Webhook Response

*This model accepts additional fields of type Any.*

## Structure

`ListServiceConversationScopedWebhookResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `webhooks` | [`List[ServiceConversationScopedWebhook]`](../../doc/models/service-conversation-scoped-webhook.md) | Optional | - |
| `meta` | [`Meta`](../../doc/models/meta.md) | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "webhooks": [
    {
      "sid": "sid2",
      "account_sid": "account_sid2",
      "chat_service_sid": "chat_service_sid6",
      "conversation_sid": "conversation_sid8",
      "target": "target6",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "sid": "sid2",
      "account_sid": "account_sid2",
      "chat_service_sid": "chat_service_sid6",
      "conversation_sid": "conversation_sid8",
      "target": "target6",
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

