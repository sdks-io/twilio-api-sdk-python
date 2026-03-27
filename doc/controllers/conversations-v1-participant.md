# Conversations V1 Participant

```python
conversations_v_1_participant_api = client.conversations_v_1_participant
```

## Class Name

`ConversationsV1ParticipantApi`

## Methods

* [Create Conversation Participant](../../doc/controllers/conversations-v1-participant.md#create-conversation-participant)
* [List Conversation Participant](../../doc/controllers/conversations-v1-participant.md#list-conversation-participant)
* [Update Conversation Participant](../../doc/controllers/conversations-v1-participant.md#update-conversation-participant)
* [Delete Conversation Participant](../../doc/controllers/conversations-v1-participant.md#delete-conversation-participant)
* [Fetch Conversation Participant](../../doc/controllers/conversations-v1-participant.md#fetch-conversation-participant)
* [Create Service Conversation Participant](../../doc/controllers/conversations-v1-participant.md#create-service-conversation-participant)
* [List Service Conversation Participant](../../doc/controllers/conversations-v1-participant.md#list-service-conversation-participant)
* [Update Service Conversation Participant](../../doc/controllers/conversations-v1-participant.md#update-service-conversation-participant)
* [Delete Service Conversation Participant](../../doc/controllers/conversations-v1-participant.md#delete-service-conversation-participant)
* [Fetch Service Conversation Participant](../../doc/controllers/conversations-v1-participant.md#fetch-service-conversation-participant)


# Create Conversation Participant

Add a new participant to the conversation

```python
def create_conversation_participant(self,
                                   conversation_sid,
                                   x_twilio_webhook_enabled=None,
                                   identity=None,
                                   messaging_binding_address=None,
                                   messaging_binding_proxy_address=None,
                                   date_created=None,
                                   date_updated=None,
                                   attributes=None,
                                   messaging_binding_projected_address=None,
                                   role_sid=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for this participant. |
| `x_twilio_webhook_enabled` | [`ChannelWebhookEnabledType`](../../doc/models/channel-webhook-enabled-type.md) | Header, Optional | The X-Twilio-Webhook-Enabled HTTP request header |
| `identity` | `str` | Form, Optional | A unique string identifier for the conversation participant as [Conversation User](https://www.twilio.com/docs/conversations/api/user-resource). This parameter is non-null if (and only if) the participant is using the Conversations SDK to communicate. Limited to 256 characters. |
| `messaging_binding_address` | `str` | Form, Optional | The address of the participant's device, e.g. a phone or WhatsApp number. Together with the Proxy address, this determines a participant uniquely. This field (with proxy_address) is only null when the participant is interacting from an SDK endpoint (see the 'identity' field). |
| `messaging_binding_proxy_address` | `str` | Form, Optional | The address of the Twilio phone number (or WhatsApp number) that the participant is in contact with. This field, together with participant address, is only null when the participant is interacting from an SDK endpoint (see the 'identity' field). |
| `date_created` | `datetime` | Form, Optional | The date that this resource was created. |
| `date_updated` | `datetime` | Form, Optional | The date that this resource was last updated. |
| `attributes` | `str` | Form, Optional | An optional string metadata field you can use to store any data you wish. The string value must contain structurally valid JSON if specified.  **Note** that if the attributes are not set "{}" will be returned. |
| `messaging_binding_projected_address` | `str` | Form, Optional | The address of the Twilio phone number that is used in Group MMS. Communication mask for the Conversation participant with Identity. |
| `role_sid` | `str` | Form, Optional | The SID of a conversation-level [Role](https://www.twilio.com/docs/conversations/api/role-resource) to assign to the participant.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^RL[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConversationParticipant`](../../doc/models/conversation-participant.md).

## Example Usage

```python
conversation_sid = 'ConversationSid0'

identity = 'IDENTITY'

messaging_binding_address = '+15558675310'

messaging_binding_proxy_address = '+15017122661'

date_created = dateutil.parser.parse('12/16/2015 22:18:37')

date_updated = dateutil.parser.parse('12/16/2015 22:18:38')

attributes = '{ "role": "driver" }'

messaging_binding_projected_address = '+15017122661'

role_sid = 'RLaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

result = conversations_v_1_participant_api.create_conversation_participant(
    conversation_sid,
    identity=identity,
    messaging_binding_address=messaging_binding_address,
    messaging_binding_proxy_address=messaging_binding_proxy_address,
    date_created=date_created,
    date_updated=date_updated,
    attributes=attributes,
    messaging_binding_projected_address=messaging_binding_projected_address,
    role_sid=role_sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# List Conversation Participant

Retrieve a list of all participants of the conversation

```python
def list_conversation_participant(self,
                                 conversation_sid,
                                 page_size=None,
                                 page=None,
                                 page_token=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for participants. |
| `page_size` | `int` | Query, Optional | How many resources to return in each list page. The default is 50, and the maximum is 100.<br><br>**Constraints**: `>= 1`, `<= 100` |
| `page` | `int` | Query, Optional | The page index. This value is simply for client state.<br><br>**Constraints**: `>= 0` |
| `page_token` | `str` | Query, Optional | The page token. This is provided by the API. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ListConversationParticipantResponse`](../../doc/models/list-conversation-participant-response.md).

## Example Usage

```python
conversation_sid = 'ConversationSid0'

result = conversations_v_1_participant_api.list_conversation_participant(conversation_sid)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Update Conversation Participant

Update an existing participant in the conversation

```python
def update_conversation_participant(self,
                                   conversation_sid,
                                   sid,
                                   x_twilio_webhook_enabled=None,
                                   date_created=None,
                                   date_updated=None,
                                   attributes=None,
                                   role_sid=None,
                                   messaging_binding_proxy_address=None,
                                   messaging_binding_projected_address=None,
                                   identity=None,
                                   last_read_message_index=None,
                                   last_read_timestamp=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for this participant. |
| `sid` | `str` | Template, Required | A 34 character string that uniquely identifies this resource. |
| `x_twilio_webhook_enabled` | [`ChannelWebhookEnabledType`](../../doc/models/channel-webhook-enabled-type.md) | Header, Optional | The X-Twilio-Webhook-Enabled HTTP request header |
| `date_created` | `datetime` | Form, Optional | The date that this resource was created. |
| `date_updated` | `datetime` | Form, Optional | The date that this resource was last updated. |
| `attributes` | `str` | Form, Optional | An optional string metadata field you can use to store any data you wish. The string value must contain structurally valid JSON if specified.  **Note** that if the attributes are not set "{}" will be returned. |
| `role_sid` | `str` | Form, Optional | The SID of a conversation-level [Role](https://www.twilio.com/docs/conversations/api/role-resource) to assign to the participant.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^RL[0-9a-fA-F]{32}$` |
| `messaging_binding_proxy_address` | `str` | Form, Optional | The address of the Twilio phone number that the participant is in contact with. 'null' value will remove it. |
| `messaging_binding_projected_address` | `str` | Form, Optional | The address of the Twilio phone number that is used in Group MMS. 'null' value will remove it. |
| `identity` | `str` | Form, Optional | A unique string identifier for the conversation participant as [Conversation User](https://www.twilio.com/docs/conversations/api/user-resource). This parameter is non-null if (and only if) the participant is using the Conversations SDK to communicate. Limited to 256 characters. |
| `last_read_message_index` | `int` | Form, Optional | Index of last “read” message in the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for the Participant. |
| `last_read_timestamp` | `str` | Form, Optional | Timestamp of last “read” message in the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for the Participant. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConversationParticipant`](../../doc/models/conversation-participant.md).

## Example Usage

```python
conversation_sid = 'ConversationSid0'

sid = 'Sid8'

date_created = dateutil.parser.parse('12/16/2015 22:18:37')

date_updated = dateutil.parser.parse('12/16/2015 22:18:38')

attributes = '{ "role": "driver" }'

role_sid = 'RLaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

messaging_binding_projected_address = '+15017122661'

result = conversations_v_1_participant_api.update_conversation_participant(
    conversation_sid,
    sid,
    date_created=date_created,
    date_updated=date_updated,
    attributes=attributes,
    role_sid=role_sid,
    messaging_binding_projected_address=messaging_binding_projected_address
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Delete Conversation Participant

Remove a participant from the conversation

```python
def delete_conversation_participant(self,
                                   conversation_sid,
                                   sid,
                                   x_twilio_webhook_enabled=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for this participant. |
| `sid` | `str` | Template, Required | A 34 character string that uniquely identifies this resource. |
| `x_twilio_webhook_enabled` | [`ChannelWebhookEnabledType`](../../doc/models/channel-webhook-enabled-type.md) | Header, Optional | The X-Twilio-Webhook-Enabled HTTP request header |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```python
conversation_sid = 'ConversationSid0'

sid = 'Sid8'

result = conversations_v_1_participant_api.delete_conversation_participant(
    conversation_sid,
    sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Fetch Conversation Participant

Fetch a participant of the conversation

```python
def fetch_conversation_participant(self,
                                  conversation_sid,
                                  sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for this participant. |
| `sid` | `str` | Template, Required | A 34 character string that uniquely identifies this resource. Alternatively, you can pass a Participant's `identity` rather than the SID. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConversationParticipant`](../../doc/models/conversation-participant.md).

## Example Usage

```python
conversation_sid = 'ConversationSid0'

sid = 'Sid8'

result = conversations_v_1_participant_api.fetch_conversation_participant(
    conversation_sid,
    sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Create Service Conversation Participant

Add a new participant to the conversation in a specific service

```python
def create_service_conversation_participant(self,
                                           chat_service_sid,
                                           conversation_sid,
                                           x_twilio_webhook_enabled=None,
                                           identity=None,
                                           messaging_binding_address=None,
                                           messaging_binding_proxy_address=None,
                                           date_created=None,
                                           date_updated=None,
                                           attributes=None,
                                           messaging_binding_projected_address=None,
                                           role_sid=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Participant resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for this participant. |
| `x_twilio_webhook_enabled` | [`ChannelWebhookEnabledType`](../../doc/models/channel-webhook-enabled-type.md) | Header, Optional | The X-Twilio-Webhook-Enabled HTTP request header |
| `identity` | `str` | Form, Optional | A unique string identifier for the conversation participant as [Conversation User](https://www.twilio.com/docs/conversations/api/user-resource). This parameter is non-null if (and only if) the participant is using the [Conversation SDK](https://www.twilio.com/docs/conversations/sdk-overview) to communicate. Limited to 256 characters. |
| `messaging_binding_address` | `str` | Form, Optional | The address of the participant's device, e.g. a phone or WhatsApp number. Together with the Proxy address, this determines a participant uniquely. This field (with `proxy_address`) is only null when the participant is interacting from an SDK endpoint (see the `identity` field). |
| `messaging_binding_proxy_address` | `str` | Form, Optional | The address of the Twilio phone number (or WhatsApp number) that the participant is in contact with. This field, together with participant address, is only null when the participant is interacting from an SDK endpoint (see the `identity` field). |
| `date_created` | `datetime` | Form, Optional | The date on which this resource was created. |
| `date_updated` | `datetime` | Form, Optional | The date on which this resource was last updated. |
| `attributes` | `str` | Form, Optional | An optional string metadata field you can use to store any data you wish. The string value must contain structurally valid JSON if specified.  **Note** that if the attributes are not set `{}` will be returned. |
| `messaging_binding_projected_address` | `str` | Form, Optional | The address of the Twilio phone number that is used in Group MMS. |
| `role_sid` | `str` | Form, Optional | The SID of a conversation-level [Role](https://www.twilio.com/docs/conversations/api/role-resource) to assign to the participant.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^RL[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ServiceConversationParticipant`](../../doc/models/service-conversation-participant.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

conversation_sid = 'ConversationSid0'

identity = 'IDENTITY'

messaging_binding_address = '+15558675310'

messaging_binding_proxy_address = '+15017122661'

date_created = dateutil.parser.parse('12/16/2015 22:18:37')

date_updated = dateutil.parser.parse('12/16/2015 22:18:38')

attributes = '{ "role": "driver" }'

messaging_binding_projected_address = '+15017122661'

role_sid = 'RLaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

result = conversations_v_1_participant_api.create_service_conversation_participant(
    chat_service_sid,
    conversation_sid,
    identity=identity,
    messaging_binding_address=messaging_binding_address,
    messaging_binding_proxy_address=messaging_binding_proxy_address,
    date_created=date_created,
    date_updated=date_updated,
    attributes=attributes,
    messaging_binding_projected_address=messaging_binding_projected_address,
    role_sid=role_sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# List Service Conversation Participant

Retrieve a list of all participants of the conversation

```python
def list_service_conversation_participant(self,
                                         chat_service_sid,
                                         conversation_sid,
                                         page_size=None,
                                         page=None,
                                         page_token=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Participant resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for participants. |
| `page_size` | `int` | Query, Optional | How many resources to return in each list page. The default is 50, and the maximum is 100.<br><br>**Constraints**: `>= 1`, `<= 100` |
| `page` | `int` | Query, Optional | The page index. This value is simply for client state.<br><br>**Constraints**: `>= 0` |
| `page_token` | `str` | Query, Optional | The page token. This is provided by the API. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ListServiceConversationParticipantResponse`](../../doc/models/list-service-conversation-participant-response.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

conversation_sid = 'ConversationSid0'

result = conversations_v_1_participant_api.list_service_conversation_participant(
    chat_service_sid,
    conversation_sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Update Service Conversation Participant

Update an existing participant in the conversation

```python
def update_service_conversation_participant(self,
                                           chat_service_sid,
                                           conversation_sid,
                                           sid,
                                           x_twilio_webhook_enabled=None,
                                           date_created=None,
                                           date_updated=None,
                                           identity=None,
                                           attributes=None,
                                           role_sid=None,
                                           messaging_binding_proxy_address=None,
                                           messaging_binding_projected_address=None,
                                           last_read_message_index=None,
                                           last_read_timestamp=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Participant resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for this participant. |
| `sid` | `str` | Template, Required | A 34 character string that uniquely identifies this resource. |
| `x_twilio_webhook_enabled` | [`ChannelWebhookEnabledType`](../../doc/models/channel-webhook-enabled-type.md) | Header, Optional | The X-Twilio-Webhook-Enabled HTTP request header |
| `date_created` | `datetime` | Form, Optional | The date on which this resource was created. |
| `date_updated` | `datetime` | Form, Optional | The date on which this resource was last updated. |
| `identity` | `str` | Form, Optional | A unique string identifier for the conversation participant as [Conversation User](https://www.twilio.com/docs/conversations/api/user-resource). This parameter is non-null if (and only if) the participant is using the [Conversation SDK](https://www.twilio.com/docs/conversations/sdk-overview) to communicate. Limited to 256 characters. |
| `attributes` | `str` | Form, Optional | An optional string metadata field you can use to store any data you wish. The string value must contain structurally valid JSON if specified.  **Note** that if the attributes are not set `{}` will be returned. |
| `role_sid` | `str` | Form, Optional | The SID of a conversation-level [Role](https://www.twilio.com/docs/conversations/api/role-resource) to assign to the participant.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^RL[0-9a-fA-F]{32}$` |
| `messaging_binding_proxy_address` | `str` | Form, Optional | The address of the Twilio phone number that the participant is in contact with. 'null' value will remove it. |
| `messaging_binding_projected_address` | `str` | Form, Optional | The address of the Twilio phone number that is used in Group MMS. 'null' value will remove it. |
| `last_read_message_index` | `int` | Form, Optional | Index of last “read” message in the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for the Participant. |
| `last_read_timestamp` | `str` | Form, Optional | Timestamp of last “read” message in the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for the Participant. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ServiceConversationParticipant`](../../doc/models/service-conversation-participant.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

conversation_sid = 'ConversationSid0'

sid = 'Sid8'

date_created = dateutil.parser.parse('12/16/2015 22:18:37')

date_updated = dateutil.parser.parse('12/16/2015 22:18:38')

attributes = '{ "role": "driver" }'

role_sid = 'RLaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

messaging_binding_projected_address = '+15017122661'

result = conversations_v_1_participant_api.update_service_conversation_participant(
    chat_service_sid,
    conversation_sid,
    sid,
    date_created=date_created,
    date_updated=date_updated,
    attributes=attributes,
    role_sid=role_sid,
    messaging_binding_projected_address=messaging_binding_projected_address
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Delete Service Conversation Participant

Remove a participant from the conversation

```python
def delete_service_conversation_participant(self,
                                           chat_service_sid,
                                           conversation_sid,
                                           sid,
                                           x_twilio_webhook_enabled=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Participant resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for this participant. |
| `sid` | `str` | Template, Required | A 34 character string that uniquely identifies this resource. |
| `x_twilio_webhook_enabled` | [`ChannelWebhookEnabledType`](../../doc/models/channel-webhook-enabled-type.md) | Header, Optional | The X-Twilio-Webhook-Enabled HTTP request header |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

conversation_sid = 'ConversationSid0'

sid = 'Sid8'

result = conversations_v_1_participant_api.delete_service_conversation_participant(
    chat_service_sid,
    conversation_sid,
    sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Fetch Service Conversation Participant

Fetch a participant of the conversation

```python
def fetch_service_conversation_participant(self,
                                          chat_service_sid,
                                          conversation_sid,
                                          sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Participant resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for this participant. |
| `sid` | `str` | Template, Required | A 34 character string that uniquely identifies this resource. Alternatively, you can pass a Participant's `identity` rather than the SID. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ServiceConversationParticipant`](../../doc/models/service-conversation-participant.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

conversation_sid = 'ConversationSid0'

sid = 'Sid8'

result = conversations_v_1_participant_api.fetch_service_conversation_participant(
    chat_service_sid,
    conversation_sid,
    sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

