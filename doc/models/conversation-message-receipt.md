
# Conversation Message Receipt

*This model accepts additional fields of type Any.*

## Structure

`ConversationMessageReceipt`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `account_sid` | `str` | Optional | The unique ID of the [Account](https://www.twilio.com/docs/iam/api/account) responsible for this participant.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^AC[0-9a-fA-F]{32}$` |
| `conversation_sid` | `str` | Optional | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for this message.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^CH[0-9a-fA-F]{32}$` |
| `sid` | `str` | Optional | A 34 character string that uniquely identifies this resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^DY[0-9a-fA-F]{32}$` |
| `message_sid` | `str` | Optional | The SID of the message within a [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) the delivery receipt belongs to<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IM[0-9a-fA-F]{32}$` |
| `channel_message_sid` | `str` | Optional | A messaging channel-specific identifier for the message delivered to participant e.g. `SMxx` for SMS, `WAxx` for Whatsapp etc.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^[a-zA-Z]{2}[0-9a-fA-F]{32}$` |
| `participant_sid` | `str` | Optional | The unique ID of the participant the delivery receipt belongs to.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^MB[0-9a-fA-F]{32}$` |
| `status` | [`ConversationMessageReceiptDeliveryStatus`](../../doc/models/conversation-message-receipt-delivery-status.md) | Optional | The message delivery status, can be `read`, `failed`, `delivered`, `undelivered`, `sent` or null. |
| `error_code` | `int` | Optional | The message [delivery error code](https://www.twilio.com/docs/sms/api/message-resource#delivery-related-errors) for a `failed` status,<br><br>**Default**: `0` |
| `date_created` | `datetime` | Optional | The date that this resource was created. |
| `date_updated` | `datetime` | Optional | The date that this resource was last updated. `null` if the delivery receipt has not been updated. |
| `url` | `str` | Optional | An absolute API resource URL for this delivery receipt. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "error_code": 0,
  "account_sid": "account_sid0",
  "conversation_sid": "conversation_sid0",
  "sid": "sid4",
  "message_sid": "message_sid2",
  "channel_message_sid": "channel_message_sid0",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

