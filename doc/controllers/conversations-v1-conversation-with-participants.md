# Conversations V1 Conversation with Participants

```python
conversations_v_1_conversation_with_participants_api = client.conversations_v_1_conversation_with_participants
```

## Class Name

`ConversationsV1ConversationWithParticipantsApi`

## Methods

* [Create Conversation with Participants](../../doc/controllers/conversations-v1-conversation-with-participants.md#create-conversation-with-participants)
* [Create Service Conversation with Participants](../../doc/controllers/conversations-v1-conversation-with-participants.md#create-service-conversation-with-participants)


# Create Conversation with Participants

Create a new conversation with the list of participants in your account's default service

```python
def create_conversation_with_participants(self,
                                         x_twilio_webhook_enabled=None,
                                         friendly_name=None,
                                         unique_name=None,
                                         date_created=None,
                                         date_updated=None,
                                         messaging_service_sid=None,
                                         attributes=None,
                                         state=None,
                                         timers_inactive=None,
                                         timers_closed=None,
                                         bindings_email_address=None,
                                         bindings_email_name=None,
                                         participant=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `x_twilio_webhook_enabled` | [`ChannelWebhookEnabledType`](../../doc/models/channel-webhook-enabled-type.md) | Header, Optional | The X-Twilio-Webhook-Enabled HTTP request header |
| `friendly_name` | `str` | Form, Optional | The human-readable name of this conversation, limited to 256 characters. Optional. |
| `unique_name` | `str` | Form, Optional | An application-defined string that uniquely identifies the resource. It can be used to address the resource in place of the resource's `sid` in the URL. |
| `date_created` | `datetime` | Form, Optional | The date that this resource was created. |
| `date_updated` | `datetime` | Form, Optional | The date that this resource was last updated. |
| `messaging_service_sid` | `str` | Form, Optional | The unique ID of the [Messaging Service](https://www.twilio.com/docs/messaging/api/service-resource) this conversation belongs to.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^MG[0-9a-fA-F]{32}$` |
| `attributes` | `str` | Form, Optional | An optional string metadata field you can use to store any data you wish. The string value must contain structurally valid JSON if specified.  **Note** that if the attributes are not set "{}" will be returned. |
| `state` | [`ConversationWithParticipantsState`](../../doc/models/conversation-with-participants-state.md) | Form, Optional | Current state of this conversation. Can be either `initializing`, `active`, `inactive` or `closed` and defaults to `active` |
| `timers_inactive` | `str` | Form, Optional | ISO8601 duration when conversation will be switched to `inactive` state. Minimum value for this timer is 1 minute. |
| `timers_closed` | `str` | Form, Optional | ISO8601 duration when conversation will be switched to `closed` state. Minimum value for this timer is 10 minutes. |
| `bindings_email_address` | `str` | Form, Optional | The default email address that will be used when sending outbound emails in this conversation. |
| `bindings_email_name` | `str` | Form, Optional | The default name that will be used when sending outbound emails in this conversation. |
| `participant` | `List[str]` | Form, Optional | The participant to be added to the conversation in JSON format. The JSON object attributes are as parameters in [Participant Resource](https://www.twilio.com/docs/conversations/api/conversation-participant-resource). The maximum number of participants that can be added in a single request is 10. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConversationWithParticipants`](../../doc/models/conversation-with-participants.md).

## Example Usage

```python
friendly_name = 'friendly_name'

unique_name = 'unique_name'

date_created = dateutil.parser.parse('12/16/2015 22:18:37')

date_updated = dateutil.parser.parse('12/16/2015 22:18:38')

messaging_service_sid = 'MGaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

attributes = '{ "topic": "feedback" }'

state = ConversationWithParticipantsState.INACTIVE

timers_inactive = 'PT1M'

timers_closed = 'PT10M'

result = conversations_v_1_conversation_with_participants_api.create_conversation_with_participants(
    friendly_name=friendly_name,
    unique_name=unique_name,
    date_created=date_created,
    date_updated=date_updated,
    messaging_service_sid=messaging_service_sid,
    attributes=attributes,
    state=state,
    timers_inactive=timers_inactive,
    timers_closed=timers_closed
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Create Service Conversation with Participants

Create a new conversation with the list of participants in your account's default service

```python
def create_service_conversation_with_participants(self,
                                                 chat_service_sid,
                                                 x_twilio_webhook_enabled=None,
                                                 friendly_name=None,
                                                 unique_name=None,
                                                 date_created=None,
                                                 date_updated=None,
                                                 messaging_service_sid=None,
                                                 attributes=None,
                                                 state=None,
                                                 timers_inactive=None,
                                                 timers_closed=None,
                                                 bindings_email_address=None,
                                                 bindings_email_name=None,
                                                 participant=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Conversation resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `x_twilio_webhook_enabled` | [`ChannelWebhookEnabledType`](../../doc/models/channel-webhook-enabled-type.md) | Header, Optional | The X-Twilio-Webhook-Enabled HTTP request header |
| `friendly_name` | `str` | Form, Optional | The human-readable name of this conversation, limited to 256 characters. Optional. |
| `unique_name` | `str` | Form, Optional | An application-defined string that uniquely identifies the resource. It can be used to address the resource in place of the resource's `sid` in the URL. |
| `date_created` | `datetime` | Form, Optional | The date that this resource was created. |
| `date_updated` | `datetime` | Form, Optional | The date that this resource was last updated. |
| `messaging_service_sid` | `str` | Form, Optional | The unique ID of the [Messaging Service](https://www.twilio.com/docs/messaging/api/service-resource) this conversation belongs to.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^MG[0-9a-fA-F]{32}$` |
| `attributes` | `str` | Form, Optional | An optional string metadata field you can use to store any data you wish. The string value must contain structurally valid JSON if specified.  **Note** that if the attributes are not set "{}" will be returned. |
| `state` | [`ServiceConversationWithParticipantsState`](../../doc/models/service-conversation-with-participants-state.md) | Form, Optional | Current state of this conversation. Can be either `initializing`, `active`, `inactive` or `closed` and defaults to `active` |
| `timers_inactive` | `str` | Form, Optional | ISO8601 duration when conversation will be switched to `inactive` state. Minimum value for this timer is 1 minute. |
| `timers_closed` | `str` | Form, Optional | ISO8601 duration when conversation will be switched to `closed` state. Minimum value for this timer is 10 minutes. |
| `bindings_email_address` | `str` | Form, Optional | The default email address that will be used when sending outbound emails in this conversation. |
| `bindings_email_name` | `str` | Form, Optional | The default name that will be used when sending outbound emails in this conversation. |
| `participant` | `List[str]` | Form, Optional | The participant to be added to the conversation in JSON format. The JSON object attributes are as parameters in [Participant Resource](https://www.twilio.com/docs/conversations/api/conversation-participant-resource). The maximum number of participants that can be added in a single request is 10. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ServiceConversationWithParticipants`](../../doc/models/service-conversation-with-participants.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

friendly_name = 'friendly_name'

unique_name = 'unique_name'

date_created = dateutil.parser.parse('12/16/2015 22:18:37')

date_updated = dateutil.parser.parse('12/16/2015 22:18:38')

messaging_service_sid = 'MGaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

attributes = '{ "topic": "feedback" }'

state = ServiceConversationWithParticipantsState.INACTIVE

timers_inactive = 'PT1M'

timers_closed = 'PT10M'

participant = [
    '{ "identity": "user1" }',
    '{ "identity": "user2" }'
]

result = conversations_v_1_conversation_with_participants_api.create_service_conversation_with_participants(
    chat_service_sid,
    friendly_name=friendly_name,
    unique_name=unique_name,
    date_created=date_created,
    date_updated=date_updated,
    messaging_service_sid=messaging_service_sid,
    attributes=attributes,
    state=state,
    timers_inactive=timers_inactive,
    timers_closed=timers_closed,
    participant=participant
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

