
# Configuration Webhook

*This model accepts additional fields of type Any.*

## Structure

`ConfigurationWebhook`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `account_sid` | `str` | Optional | The unique ID of the [Account](https://www.twilio.com/docs/iam/api/account) responsible for this conversation.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^AC[0-9a-fA-F]{32}$` |
| `method` | [`ConfigurationWebhookMethod`](../../doc/models/configuration-webhook-method.md) | Optional | The HTTP method to be used when sending a webhook request. |
| `filters` | `List[str]` | Optional | The list of webhook event triggers that are enabled for this Service: `onMessageAdded`, `onMessageUpdated`, `onMessageRemoved`, `onMessageAdd`, `onMessageUpdate`, `onMessageRemove`, `onConversationUpdated`, `onConversationRemoved`, `onConversationAdd`, `onConversationAdded`, `onConversationRemove`, `onConversationUpdate`, `onConversationStateUpdated`, `onParticipantAdded`, `onParticipantUpdated`, `onParticipantRemoved`, `onParticipantAdd`, `onParticipantRemove`, `onParticipantUpdate`, `onDeliveryUpdated`, `onUserAdded`, `onUserUpdate`, `onUserUpdated` |
| `pre_webhook_url` | `str` | Optional | The absolute url the pre-event webhook request should be sent to. |
| `post_webhook_url` | `str` | Optional | The absolute url the post-event webhook request should be sent to. |
| `target` | [`ConfigurationWebhookTarget`](../../doc/models/configuration-webhook-target.md) | Optional | The routing target of the webhook. Can be ordinary or route internally to Flex |
| `url` | `str` | Optional | An absolute API resource API resource URL for this webhook. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "account_sid": "account_sid4",
  "method": "GET",
  "filters": [
    "filters8",
    "filters7"
  ],
  "pre_webhook_url": "pre_webhook_url0",
  "post_webhook_url": "post_webhook_url4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

