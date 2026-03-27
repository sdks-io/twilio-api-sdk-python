
# Service Webhook Configuration

*This model accepts additional fields of type Any.*

## Structure

`ServiceWebhookConfiguration`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `account_sid` | `str` | Optional | The unique ID of the [Account](https://www.twilio.com/docs/iam/api/account) responsible for this service.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^AC[0-9a-fA-F]{32}$` |
| `chat_service_sid` | `str` | Optional | The unique ID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) this conversation belongs to.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `pre_webhook_url` | `str` | Optional | The absolute url the pre-event webhook request should be sent to. |
| `post_webhook_url` | `str` | Optional | The absolute url the post-event webhook request should be sent to. |
| `filters` | `List[str]` | Optional | The list of events that your configured webhook targets will receive. Events not configured here will not fire. Possible values are `onParticipantAdd`, `onParticipantAdded`, `onDeliveryUpdated`, `onConversationUpdated`, `onConversationRemove`, `onParticipantRemove`, `onConversationUpdate`, `onMessageAdd`, `onMessageRemoved`, `onParticipantUpdated`, `onConversationAdded`, `onMessageAdded`, `onConversationAdd`, `onConversationRemoved`, `onParticipantUpdate`, `onMessageRemove`, `onMessageUpdated`, `onParticipantRemoved`, `onMessageUpdate` or `onConversationStateUpdated`. |
| `method` | [`ServiceWebhookConfigurationMethod`](../../doc/models/service-webhook-configuration-method.md) | Optional | The HTTP method to be used when sending a webhook request. One of `GET` or `POST`. |
| `url` | `str` | Optional | An absolute API resource URL for this webhook. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "account_sid": "account_sid2",
  "chat_service_sid": "chat_service_sid6",
  "pre_webhook_url": "pre_webhook_url8",
  "post_webhook_url": "post_webhook_url2",
  "filters": [
    "filters6",
    "filters5"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

