# Conversations V1 Message

```python
conversations_v_1_message_api = client.conversations_v_1_message
```

## Class Name

`ConversationsV1MessageApi`

## Methods

* [Create Conversation Message](../../doc/controllers/conversations-v1-message.md#create-conversation-message)
* [List Conversation Message](../../doc/controllers/conversations-v1-message.md#list-conversation-message)
* [Update Conversation Message](../../doc/controllers/conversations-v1-message.md#update-conversation-message)
* [Delete Conversation Message](../../doc/controllers/conversations-v1-message.md#delete-conversation-message)
* [Fetch Conversation Message](../../doc/controllers/conversations-v1-message.md#fetch-conversation-message)
* [Create Service Conversation Message](../../doc/controllers/conversations-v1-message.md#create-service-conversation-message)
* [List Service Conversation Message](../../doc/controllers/conversations-v1-message.md#list-service-conversation-message)
* [Update Service Conversation Message](../../doc/controllers/conversations-v1-message.md#update-service-conversation-message)
* [Delete Service Conversation Message](../../doc/controllers/conversations-v1-message.md#delete-service-conversation-message)
* [Fetch Service Conversation Message](../../doc/controllers/conversations-v1-message.md#fetch-service-conversation-message)


# Create Conversation Message

Add a new message to the conversation

```python
def create_conversation_message(self,
                               conversation_sid,
                               x_twilio_webhook_enabled=None,
                               author=None,
                               body=None,
                               date_created=None,
                               date_updated=None,
                               attributes=None,
                               media_sid=None,
                               content_sid=None,
                               content_variables=None,
                               subject=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for this message. |
| `x_twilio_webhook_enabled` | [`ChannelWebhookEnabledType`](../../doc/models/channel-webhook-enabled-type.md) | Header, Optional | The X-Twilio-Webhook-Enabled HTTP request header |
| `author` | `str` | Form, Optional | The channel specific identifier of the message's author. Defaults to `system`. |
| `body` | `str` | Form, Optional | The content of the message, can be up to 1,600 characters long. |
| `date_created` | `datetime` | Form, Optional | The date that this resource was created. |
| `date_updated` | `datetime` | Form, Optional | The date that this resource was last updated. `null` if the message has not been edited. |
| `attributes` | `str` | Form, Optional | A string metadata field you can use to store any data you wish. The string value must contain structurally valid JSON if specified.  **Note** that if the attributes are not set "{}" will be returned. |
| `media_sid` | `str` | Form, Optional | The Media SID to be attached to the new Message.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^ME[0-9a-fA-F]{32}$` |
| `content_sid` | `str` | Form, Optional | The unique ID of the multi-channel [Rich Content](https://www.twilio.com/docs/content) template, required for template-generated messages.  **Note** that if this field is set, `Body` and `MediaSid` parameters are ignored.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^HX[0-9a-fA-F]{32}$` |
| `content_variables` | `str` | Form, Optional | A structurally valid JSON string that contains values to resolve Rich Content template variables. |
| `subject` | `str` | Form, Optional | The subject of the message, can be up to 256 characters long. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConversationMessage`](../../doc/models/conversation-message.md).

## Example Usage

```python
conversation_sid = 'ConversationSid0'

author = 'message author'

body = 'Hello'

date_created = dateutil.parser.parse('12/16/2015 22:18:37')

date_updated = dateutil.parser.parse('12/16/2015 22:18:38')

attributes = '{ "importance": "high" }'

media_sid = 'MEaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

content_sid = 'HXaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

content_variables = '{"name": "John"}'

subject = 'message subject'

result = conversations_v_1_message_api.create_conversation_message(
    conversation_sid,
    author=author,
    body=body,
    date_created=date_created,
    date_updated=date_updated,
    attributes=attributes,
    media_sid=media_sid,
    content_sid=content_sid,
    content_variables=content_variables,
    subject=subject
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# List Conversation Message

Retrieve a list of all messages in the conversation

```python
def list_conversation_message(self,
                             conversation_sid,
                             order=None,
                             page_size=None,
                             page=None,
                             page_token=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for messages. |
| `order` | [`ConversationMessageOrderType`](../../doc/models/conversation-message-order-type.md) | Query, Optional | The sort order of the returned messages. Can be: `asc` (ascending) or `desc` (descending), with `asc` as the default. |
| `page_size` | `int` | Query, Optional | How many resources to return in each list page. The default is 50, and the maximum is 100.<br><br>**Constraints**: `>= 1`, `<= 100` |
| `page` | `int` | Query, Optional | The page index. This value is simply for client state.<br><br>**Constraints**: `>= 0` |
| `page_token` | `str` | Query, Optional | The page token. This is provided by the API. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ListConversationMessageResponse`](../../doc/models/list-conversation-message-response.md).

## Example Usage

```python
conversation_sid = 'ConversationSid0'

order = ConversationMessageOrderType.DESC

result = conversations_v_1_message_api.list_conversation_message(
    conversation_sid,
    order=order
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Update Conversation Message

Update an existing message in the conversation

```python
def update_conversation_message(self,
                               conversation_sid,
                               sid,
                               x_twilio_webhook_enabled=None,
                               author=None,
                               body=None,
                               date_created=None,
                               date_updated=None,
                               attributes=None,
                               subject=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for this message. |
| `sid` | `str` | Template, Required | A 34 character string that uniquely identifies this resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IM[0-9a-fA-F]{32}$` |
| `x_twilio_webhook_enabled` | [`ChannelWebhookEnabledType`](../../doc/models/channel-webhook-enabled-type.md) | Header, Optional | The X-Twilio-Webhook-Enabled HTTP request header |
| `author` | `str` | Form, Optional | The channel specific identifier of the message's author. Defaults to `system`. |
| `body` | `str` | Form, Optional | The content of the message, can be up to 1,600 characters long. |
| `date_created` | `datetime` | Form, Optional | The date that this resource was created. |
| `date_updated` | `datetime` | Form, Optional | The date that this resource was last updated. `null` if the message has not been edited. |
| `attributes` | `str` | Form, Optional | A string metadata field you can use to store any data you wish. The string value must contain structurally valid JSON if specified.  **Note** that if the attributes are not set "{}" will be returned. |
| `subject` | `str` | Form, Optional | The subject of the message, can be up to 256 characters long. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConversationMessage`](../../doc/models/conversation-message.md).

## Example Usage

```python
conversation_sid = 'ConversationSid0'

sid = 'Sid8'

author = 'message author'

body = 'Hello'

date_created = dateutil.parser.parse('12/16/2015 22:18:37')

date_updated = dateutil.parser.parse('12/16/2015 22:18:38')

attributes = '{ "importance": "high" }'

result = conversations_v_1_message_api.update_conversation_message(
    conversation_sid,
    sid,
    author=author,
    body=body,
    date_created=date_created,
    date_updated=date_updated,
    attributes=attributes
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Delete Conversation Message

Remove a message from the conversation

```python
def delete_conversation_message(self,
                               conversation_sid,
                               sid,
                               x_twilio_webhook_enabled=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for this message. |
| `sid` | `str` | Template, Required | A 34 character string that uniquely identifies this resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IM[0-9a-fA-F]{32}$` |
| `x_twilio_webhook_enabled` | [`ChannelWebhookEnabledType`](../../doc/models/channel-webhook-enabled-type.md) | Header, Optional | The X-Twilio-Webhook-Enabled HTTP request header |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```python
conversation_sid = 'ConversationSid0'

sid = 'Sid8'

result = conversations_v_1_message_api.delete_conversation_message(
    conversation_sid,
    sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Fetch Conversation Message

Fetch a message from the conversation

```python
def fetch_conversation_message(self,
                              conversation_sid,
                              sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for this message. |
| `sid` | `str` | Template, Required | A 34 character string that uniquely identifies this resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IM[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConversationMessage`](../../doc/models/conversation-message.md).

## Example Usage

```python
conversation_sid = 'ConversationSid0'

sid = 'Sid8'

result = conversations_v_1_message_api.fetch_conversation_message(
    conversation_sid,
    sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Create Service Conversation Message

Add a new message to the conversation in a specific service

```python
def create_service_conversation_message(self,
                                       chat_service_sid,
                                       conversation_sid,
                                       x_twilio_webhook_enabled=None,
                                       author=None,
                                       body=None,
                                       date_created=None,
                                       date_updated=None,
                                       attributes=None,
                                       media_sid=None,
                                       content_sid=None,
                                       content_variables=None,
                                       subject=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Participant resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for this message. |
| `x_twilio_webhook_enabled` | [`ChannelWebhookEnabledType`](../../doc/models/channel-webhook-enabled-type.md) | Header, Optional | The X-Twilio-Webhook-Enabled HTTP request header |
| `author` | `str` | Form, Optional | The channel specific identifier of the message's author. Defaults to `system`. |
| `body` | `str` | Form, Optional | The content of the message, can be up to 1,600 characters long. |
| `date_created` | `datetime` | Form, Optional | The date that this resource was created. |
| `date_updated` | `datetime` | Form, Optional | The date that this resource was last updated. `null` if the message has not been edited. |
| `attributes` | `str` | Form, Optional | A string metadata field you can use to store any data you wish. The string value must contain structurally valid JSON if specified.  **Note** that if the attributes are not set "{}" will be returned. |
| `media_sid` | `str` | Form, Optional | The Media SID to be attached to the new Message.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^ME[0-9a-fA-F]{32}$` |
| `content_sid` | `str` | Form, Optional | The unique ID of the multi-channel [Rich Content](https://www.twilio.com/docs/content) template, required for template-generated messages.  **Note** that if this field is set, `Body` and `MediaSid` parameters are ignored.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^HX[0-9a-fA-F]{32}$` |
| `content_variables` | `str` | Form, Optional | A structurally valid JSON string that contains values to resolve Rich Content template variables. |
| `subject` | `str` | Form, Optional | The subject of the message, can be up to 256 characters long. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ServiceConversationMessage`](../../doc/models/service-conversation-message.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

conversation_sid = 'ConversationSid0'

author = 'message author'

body = 'Hello'

date_created = dateutil.parser.parse('12/16/2015 22:18:37')

date_updated = dateutil.parser.parse('12/16/2015 22:18:38')

attributes = '{ "importance": "high" }'

media_sid = 'MEaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

content_sid = 'HXaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

content_variables = '{"name": "John"}'

subject = 'message subject'

result = conversations_v_1_message_api.create_service_conversation_message(
    chat_service_sid,
    conversation_sid,
    author=author,
    body=body,
    date_created=date_created,
    date_updated=date_updated,
    attributes=attributes,
    media_sid=media_sid,
    content_sid=content_sid,
    content_variables=content_variables,
    subject=subject
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# List Service Conversation Message

Retrieve a list of all messages in the conversation

```python
def list_service_conversation_message(self,
                                     chat_service_sid,
                                     conversation_sid,
                                     order=None,
                                     page_size=None,
                                     page=None,
                                     page_token=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Participant resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for messages. |
| `order` | [`ServiceConversationMessageOrderType`](../../doc/models/service-conversation-message-order-type.md) | Query, Optional | The sort order of the returned messages. Can be: `asc` (ascending) or `desc` (descending), with `asc` as the default. |
| `page_size` | `int` | Query, Optional | How many resources to return in each list page. The default is 50, and the maximum is 100.<br><br>**Constraints**: `>= 1`, `<= 100` |
| `page` | `int` | Query, Optional | The page index. This value is simply for client state.<br><br>**Constraints**: `>= 0` |
| `page_token` | `str` | Query, Optional | The page token. This is provided by the API. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ListServiceConversationMessageResponse`](../../doc/models/list-service-conversation-message-response.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

conversation_sid = 'ConversationSid0'

order = ServiceConversationMessageOrderType.DESC

result = conversations_v_1_message_api.list_service_conversation_message(
    chat_service_sid,
    conversation_sid,
    order=order
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Update Service Conversation Message

Update an existing message in the conversation

```python
def update_service_conversation_message(self,
                                       chat_service_sid,
                                       conversation_sid,
                                       sid,
                                       x_twilio_webhook_enabled=None,
                                       author=None,
                                       body=None,
                                       date_created=None,
                                       date_updated=None,
                                       attributes=None,
                                       subject=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Participant resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for this message. |
| `sid` | `str` | Template, Required | A 34 character string that uniquely identifies this resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IM[0-9a-fA-F]{32}$` |
| `x_twilio_webhook_enabled` | [`ChannelWebhookEnabledType`](../../doc/models/channel-webhook-enabled-type.md) | Header, Optional | The X-Twilio-Webhook-Enabled HTTP request header |
| `author` | `str` | Form, Optional | The channel specific identifier of the message's author. Defaults to `system`. |
| `body` | `str` | Form, Optional | The content of the message, can be up to 1,600 characters long. |
| `date_created` | `datetime` | Form, Optional | The date that this resource was created. |
| `date_updated` | `datetime` | Form, Optional | The date that this resource was last updated. `null` if the message has not been edited. |
| `attributes` | `str` | Form, Optional | A string metadata field you can use to store any data you wish. The string value must contain structurally valid JSON if specified.  **Note** that if the attributes are not set "{}" will be returned. |
| `subject` | `str` | Form, Optional | The subject of the message, can be up to 256 characters long. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ServiceConversationMessage`](../../doc/models/service-conversation-message.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

conversation_sid = 'ConversationSid0'

sid = 'Sid8'

author = 'message author'

body = 'Hello'

date_created = dateutil.parser.parse('12/16/2015 22:18:37')

date_updated = dateutil.parser.parse('12/16/2015 22:18:38')

attributes = '{ "importance": "high" }'

result = conversations_v_1_message_api.update_service_conversation_message(
    chat_service_sid,
    conversation_sid,
    sid,
    author=author,
    body=body,
    date_created=date_created,
    date_updated=date_updated,
    attributes=attributes
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Delete Service Conversation Message

Remove a message from the conversation

```python
def delete_service_conversation_message(self,
                                       chat_service_sid,
                                       conversation_sid,
                                       sid,
                                       x_twilio_webhook_enabled=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Participant resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for this message. |
| `sid` | `str` | Template, Required | A 34 character string that uniquely identifies this resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IM[0-9a-fA-F]{32}$` |
| `x_twilio_webhook_enabled` | [`ChannelWebhookEnabledType`](../../doc/models/channel-webhook-enabled-type.md) | Header, Optional | The X-Twilio-Webhook-Enabled HTTP request header |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

conversation_sid = 'ConversationSid0'

sid = 'Sid8'

result = conversations_v_1_message_api.delete_service_conversation_message(
    chat_service_sid,
    conversation_sid,
    sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Fetch Service Conversation Message

Fetch a message from the conversation

```python
def fetch_service_conversation_message(self,
                                      chat_service_sid,
                                      conversation_sid,
                                      sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Participant resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for this message. |
| `sid` | `str` | Template, Required | A 34 character string that uniquely identifies this resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IM[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ServiceConversationMessage`](../../doc/models/service-conversation-message.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

conversation_sid = 'ConversationSid0'

sid = 'Sid8'

result = conversations_v_1_message_api.fetch_service_conversation_message(
    chat_service_sid,
    conversation_sid,
    sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

