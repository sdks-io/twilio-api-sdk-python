# Conversations V1 Notification

```python
conversations_v_1_notification_api = client.conversations_v_1_notification
```

## Class Name

`ConversationsV1NotificationApi`

## Methods

* [Update Service Notification](../../doc/controllers/conversations-v1-notification.md#update-service-notification)
* [Fetch Service Notification](../../doc/controllers/conversations-v1-notification.md#fetch-service-notification)


# Update Service Notification

Update push notification service settings

```python
def update_service_notification(self,
                               chat_service_sid,
                               log_enabled=None,
                               new_message_enabled=None,
                               new_message_template=None,
                               new_message_sound=None,
                               new_message_badge_count_enabled=None,
                               added_to_conversation_enabled=None,
                               added_to_conversation_template=None,
                               added_to_conversation_sound=None,
                               removed_from_conversation_enabled=None,
                               removed_from_conversation_template=None,
                               removed_from_conversation_sound=None,
                               new_message_with_media_enabled=None,
                               new_message_with_media_template=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Configuration applies to.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `log_enabled` | `bool` | Form, Optional | Weather the notification logging is enabled. |
| `new_message_enabled` | `bool` | Form, Optional | Whether to send a notification when a new message is added to a conversation. The default is `false`. |
| `new_message_template` | `str` | Form, Optional | The template to use to create the notification text displayed when a new message is added to a conversation and `new_message.enabled` is `true`. |
| `new_message_sound` | `str` | Form, Optional | The name of the sound to play when a new message is added to a conversation and `new_message.enabled` is `true`. |
| `new_message_badge_count_enabled` | `bool` | Form, Optional | Whether the new message badge is enabled. The default is `false`. |
| `added_to_conversation_enabled` | `bool` | Form, Optional | Whether to send a notification when a participant is added to a conversation. The default is `false`. |
| `added_to_conversation_template` | `str` | Form, Optional | The template to use to create the notification text displayed when a participant is added to a conversation and `added_to_conversation.enabled` is `true`. |
| `added_to_conversation_sound` | `str` | Form, Optional | The name of the sound to play when a participant is added to a conversation and `added_to_conversation.enabled` is `true`. |
| `removed_from_conversation_enabled` | `bool` | Form, Optional | Whether to send a notification to a user when they are removed from a conversation. The default is `false`. |
| `removed_from_conversation_template` | `str` | Form, Optional | The template to use to create the notification text displayed to a user when they are removed from a conversation and `removed_from_conversation.enabled` is `true`. |
| `removed_from_conversation_sound` | `str` | Form, Optional | The name of the sound to play to a user when they are removed from a conversation and `removed_from_conversation.enabled` is `true`. |
| `new_message_with_media_enabled` | `bool` | Form, Optional | Whether to send a notification when a new message with media/file attachments is added to a conversation. The default is `false`. |
| `new_message_with_media_template` | `str` | Form, Optional | The template to use to create the notification text displayed when a new message with media/file attachments is added to a conversation and `new_message.attachments.enabled` is `true`. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ServiceNotification`](../../doc/models/service-notification.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

log_enabled = True

new_message_enabled = False

new_message_template = 'You have a new message in ${CONVERSATION} from ${PARTICIPANT}: ${MESSAGE}'

new_message_sound = 'ring'

new_message_badge_count_enabled = True

added_to_conversation_enabled = False

added_to_conversation_template = 'You have been added to a Conversation: ${CONVERSATION}'

added_to_conversation_sound = 'ring'

removed_from_conversation_enabled = False

removed_from_conversation_template = 'You have been removed from a Conversation: ${CONVERSATION}'

removed_from_conversation_sound = 'ring'

new_message_with_media_enabled = False

new_message_with_media_template = 'You have a new message in ${CONVERSATION} with ${MEDIA_COUNT} media files: ${MEDIA}'

result = conversations_v_1_notification_api.update_service_notification(
    chat_service_sid,
    log_enabled=log_enabled,
    new_message_enabled=new_message_enabled,
    new_message_template=new_message_template,
    new_message_sound=new_message_sound,
    new_message_badge_count_enabled=new_message_badge_count_enabled,
    added_to_conversation_enabled=added_to_conversation_enabled,
    added_to_conversation_template=added_to_conversation_template,
    added_to_conversation_sound=added_to_conversation_sound,
    removed_from_conversation_enabled=removed_from_conversation_enabled,
    removed_from_conversation_template=removed_from_conversation_template,
    removed_from_conversation_sound=removed_from_conversation_sound,
    new_message_with_media_enabled=new_message_with_media_enabled,
    new_message_with_media_template=new_message_with_media_template
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Fetch Service Notification

Fetch push notification service settings

```python
def fetch_service_notification(self,
                              chat_service_sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Configuration applies to.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ServiceNotification`](../../doc/models/service-notification.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

result = conversations_v_1_notification_api.fetch_service_notification(chat_service_sid)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

