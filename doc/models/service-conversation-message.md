
# Service Conversation Message

*This model accepts additional fields of type Any.*

## Structure

`ServiceConversationMessage`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `account_sid` | `str` | Optional | The unique ID of the [Account](https://www.twilio.com/docs/iam/api/account) responsible for this message.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^AC[0-9a-fA-F]{32}$` |
| `chat_service_sid` | `str` | Optional | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Participant resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `conversation_sid` | `str` | Optional | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for this message.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^CH[0-9a-fA-F]{32}$` |
| `sid` | `str` | Optional | A 34 character string that uniquely identifies this resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IM[0-9a-fA-F]{32}$` |
| `index` | `int` | Optional | The index of the message within the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource).<br><br>**Default**: `0` |
| `author` | `str` | Optional | The channel specific identifier of the message's author. Defaults to `system`. |
| `body` | `str` | Optional | The content of the message, can be up to 1,600 characters long. |
| `media` | `List[Any]` | Optional | An array of objects that describe the Message's media, if the message contains media. Each object contains these fields: `content_type` with the MIME type of the media, `filename` with the name of the media, `sid` with the SID of the Media resource, and `size` with the media object's file size in bytes. If the Message has no media, this value is `null`. |
| `attributes` | `str` | Optional | A string metadata field you can use to store any data you wish. The string value must contain structurally valid JSON if specified.  **Note** that if the attributes are not set "{}" will be returned. |
| `participant_sid` | `str` | Optional | The unique ID of messages's author participant. Null in case of `system` sent message.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^MB[0-9a-fA-F]{32}$` |
| `date_created` | `datetime` | Optional | The date that this resource was created. |
| `date_updated` | `datetime` | Optional | The date that this resource was last updated. `null` if the message has not been edited. |
| `delivery` | `Any` | Optional | An object that contains the summary of delivery statuses for the message to non-chat participants. |
| `url` | `str` | Optional | An absolute API resource URL for this message. |
| `links` | `Any` | Optional | Contains an absolute API resource URL to access the delivery & read receipts of this message. |
| `content_sid` | `str` | Optional | The unique ID of the multi-channel [Rich Content](https://www.twilio.com/docs/content) template.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^HX[0-9a-fA-F]{32}$` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "index": 0,
  "account_sid": "account_sid6",
  "chat_service_sid": "chat_service_sid0",
  "conversation_sid": "conversation_sid6",
  "sid": "sid2",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

