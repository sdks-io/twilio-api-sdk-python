# Conversations V1 Conversation

```python
conversations_v_1_conversation_api = client.conversations_v_1_conversation
```

## Class Name

`ConversationsV1ConversationApi`

## Methods

* [Create Conversation](../../doc/controllers/conversations-v1-conversation.md#create-conversation)
* [List Conversation](../../doc/controllers/conversations-v1-conversation.md#list-conversation)
* [Update Conversation](../../doc/controllers/conversations-v1-conversation.md#update-conversation)
* [Delete Conversation](../../doc/controllers/conversations-v1-conversation.md#delete-conversation)
* [Fetch Conversation](../../doc/controllers/conversations-v1-conversation.md#fetch-conversation)
* [Create Service Conversation](../../doc/controllers/conversations-v1-conversation.md#create-service-conversation)
* [List Service Conversation](../../doc/controllers/conversations-v1-conversation.md#list-service-conversation)
* [Update Service Conversation](../../doc/controllers/conversations-v1-conversation.md#update-service-conversation)
* [Delete Service Conversation](../../doc/controllers/conversations-v1-conversation.md#delete-service-conversation)
* [Fetch Service Conversation](../../doc/controllers/conversations-v1-conversation.md#fetch-service-conversation)


# Create Conversation

Create a new conversation in your account's default service

```python
def create_conversation(self,
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
                       bindings_email_name=None)
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
| `state` | [`ConversationState`](../../doc/models/conversation-state.md) | Form, Optional | Current state of this conversation. Can be either `initializing`, `active`, `inactive` or `closed` and defaults to `active` |
| `timers_inactive` | `str` | Form, Optional | ISO8601 duration when conversation will be switched to `inactive` state. Minimum value for this timer is 1 minute. |
| `timers_closed` | `str` | Form, Optional | ISO8601 duration when conversation will be switched to `closed` state. Minimum value for this timer is 10 minutes. |
| `bindings_email_address` | `str` | Form, Optional | The default email address that will be used when sending outbound emails in this conversation. |
| `bindings_email_name` | `str` | Form, Optional | The default name that will be used when sending outbound emails in this conversation. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Conversation`](../../doc/models/conversation.md).

## Example Usage

```python
friendly_name = 'friendly_name'

unique_name = 'unique_name'

date_created = dateutil.parser.parse('12/16/2015 22:18:37')

date_updated = dateutil.parser.parse('12/16/2015 22:18:38')

messaging_service_sid = 'MGaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

attributes = '{ "topic": "feedback" }'

state = ConversationState.INACTIVE

timers_inactive = 'PT1M'

timers_closed = 'PT10M'

result = conversations_v_1_conversation_api.create_conversation(
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


# List Conversation

Retrieve a list of conversations in your account's default service

```python
def list_conversation(self,
                     start_date=None,
                     end_date=None,
                     state=None,
                     page_size=None,
                     page=None,
                     page_token=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `start_date` | `str` | Query, Optional | Specifies the beginning of the date range for filtering Conversations based on their creation date. Conversations that were created on or after this date will be included in the results. The date must be in ISO8601 format, specifically starting at the beginning of the specified date (YYYY-MM-DDT00:00:00Z), for precise filtering. This parameter can be combined with other filters. If this filter is used, the returned list is sorted by latest conversation creation date in descending order. |
| `end_date` | `str` | Query, Optional | Defines the end of the date range for filtering conversations by their creation date. Only conversations that were created on or before this date will appear in the results.  The date must be in ISO8601 format, specifically capturing up to the end of the specified date (YYYY-MM-DDT23:59:59Z), to ensure that conversations from the entire end day are included. This parameter can be combined with other filters. If this filter is used, the returned list is sorted by latest conversation creation date in descending order. |
| `state` | [`ConversationState`](../../doc/models/conversation-state.md) | Query, Optional | State for sorting and filtering list of Conversations. Can be `active`, `inactive` or `closed` |
| `page_size` | `int` | Query, Optional | How many resources to return in each list page. The default is 50, and the maximum is 100.<br><br>**Constraints**: `>= 1`, `<= 100` |
| `page` | `int` | Query, Optional | The page index. This value is simply for client state.<br><br>**Constraints**: `>= 0` |
| `page_token` | `str` | Query, Optional | The page token. This is provided by the API. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ListConversationResponse`](../../doc/models/list-conversation-response.md).

## Example Usage

```python
result = conversations_v_1_conversation_api.list_conversation()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Update Conversation

Update an existing conversation in your account's default service

```python
def update_conversation(self,
                       sid,
                       x_twilio_webhook_enabled=None,
                       friendly_name=None,
                       date_created=None,
                       date_updated=None,
                       attributes=None,
                       messaging_service_sid=None,
                       state=None,
                       timers_inactive=None,
                       timers_closed=None,
                       unique_name=None,
                       bindings_email_address=None,
                       bindings_email_name=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sid` | `str` | Template, Required | A 34 character string that uniquely identifies this resource. Can also be the `unique_name` of the Conversation. |
| `x_twilio_webhook_enabled` | [`ChannelWebhookEnabledType`](../../doc/models/channel-webhook-enabled-type.md) | Header, Optional | The X-Twilio-Webhook-Enabled HTTP request header |
| `friendly_name` | `str` | Form, Optional | The human-readable name of this conversation, limited to 256 characters. Optional. |
| `date_created` | `datetime` | Form, Optional | The date that this resource was created. |
| `date_updated` | `datetime` | Form, Optional | The date that this resource was last updated. |
| `attributes` | `str` | Form, Optional | An optional string metadata field you can use to store any data you wish. The string value must contain structurally valid JSON if specified.  **Note** that if the attributes are not set "{}" will be returned. |
| `messaging_service_sid` | `str` | Form, Optional | The unique ID of the [Messaging Service](https://www.twilio.com/docs/messaging/api/service-resource) this conversation belongs to.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^MG[0-9a-fA-F]{32}$` |
| `state` | [`ConversationState`](../../doc/models/conversation-state.md) | Form, Optional | Current state of this conversation. Can be either `initializing`, `active`, `inactive` or `closed` and defaults to `active` |
| `timers_inactive` | `str` | Form, Optional | ISO8601 duration when conversation will be switched to `inactive` state. Minimum value for this timer is 1 minute. |
| `timers_closed` | `str` | Form, Optional | ISO8601 duration when conversation will be switched to `closed` state. Minimum value for this timer is 10 minutes. |
| `unique_name` | `str` | Form, Optional | An application-defined string that uniquely identifies the resource. It can be used to address the resource in place of the resource's `sid` in the URL. |
| `bindings_email_address` | `str` | Form, Optional | The default email address that will be used when sending outbound emails in this conversation. |
| `bindings_email_name` | `str` | Form, Optional | The default name that will be used when sending outbound emails in this conversation. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Conversation`](../../doc/models/conversation.md).

## Example Usage

```python
sid = 'Sid8'

friendly_name = 'friendly_name'

date_created = dateutil.parser.parse('12/16/2015 22:18:37')

date_updated = dateutil.parser.parse('12/16/2015 22:18:38')

attributes = '{ "topic": "feedback" }'

messaging_service_sid = 'MGaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaab'

state = ConversationState.INACTIVE

timers_inactive = 'PT1M'

timers_closed = 'PT10M'

unique_name = 'unique_name'

result = conversations_v_1_conversation_api.update_conversation(
    sid,
    friendly_name=friendly_name,
    date_created=date_created,
    date_updated=date_updated,
    attributes=attributes,
    messaging_service_sid=messaging_service_sid,
    state=state,
    timers_inactive=timers_inactive,
    timers_closed=timers_closed,
    unique_name=unique_name
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Delete Conversation

Remove a conversation from your account's default service

```python
def delete_conversation(self,
                       sid,
                       x_twilio_webhook_enabled=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sid` | `str` | Template, Required | A 34 character string that uniquely identifies this resource. Can also be the `unique_name` of the Conversation. |
| `x_twilio_webhook_enabled` | [`ChannelWebhookEnabledType`](../../doc/models/channel-webhook-enabled-type.md) | Header, Optional | The X-Twilio-Webhook-Enabled HTTP request header |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```python
sid = 'Sid8'

result = conversations_v_1_conversation_api.delete_conversation(sid)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Fetch Conversation

Fetch a conversation from your account's default service

```python
def fetch_conversation(self,
                      sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sid` | `str` | Template, Required | A 34 character string that uniquely identifies this resource. Can also be the `unique_name` of the Conversation. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Conversation`](../../doc/models/conversation.md).

## Example Usage

```python
sid = 'Sid8'

result = conversations_v_1_conversation_api.fetch_conversation(sid)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Create Service Conversation

Create a new conversation in your service

```python
def create_service_conversation(self,
                               chat_service_sid,
                               x_twilio_webhook_enabled=None,
                               friendly_name=None,
                               unique_name=None,
                               attributes=None,
                               messaging_service_sid=None,
                               date_created=None,
                               date_updated=None,
                               state=None,
                               timers_inactive=None,
                               timers_closed=None,
                               bindings_email_address=None,
                               bindings_email_name=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Conversation resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `x_twilio_webhook_enabled` | [`ChannelWebhookEnabledType`](../../doc/models/channel-webhook-enabled-type.md) | Header, Optional | The X-Twilio-Webhook-Enabled HTTP request header |
| `friendly_name` | `str` | Form, Optional | The human-readable name of this conversation, limited to 256 characters. Optional. |
| `unique_name` | `str` | Form, Optional | An application-defined string that uniquely identifies the resource. It can be used to address the resource in place of the resource's `sid` in the URL. |
| `attributes` | `str` | Form, Optional | An optional string metadata field you can use to store any data you wish. The string value must contain structurally valid JSON if specified.  **Note** that if the attributes are not set "{}" will be returned. |
| `messaging_service_sid` | `str` | Form, Optional | The unique ID of the [Messaging Service](https://www.twilio.com/docs/messaging/api/service-resource) this conversation belongs to.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^MG[0-9a-fA-F]{32}$` |
| `date_created` | `datetime` | Form, Optional | The date that this resource was created. |
| `date_updated` | `datetime` | Form, Optional | The date that this resource was last updated. |
| `state` | [`ServiceConversationState`](../../doc/models/service-conversation-state.md) | Form, Optional | Current state of this conversation. Can be either `initializing`, `active`, `inactive` or `closed` and defaults to `active` |
| `timers_inactive` | `str` | Form, Optional | ISO8601 duration when conversation will be switched to `inactive` state. Minimum value for this timer is 1 minute. |
| `timers_closed` | `str` | Form, Optional | ISO8601 duration when conversation will be switched to `closed` state. Minimum value for this timer is 10 minutes. |
| `bindings_email_address` | `str` | Form, Optional | The default email address that will be used when sending outbound emails in this conversation. |
| `bindings_email_name` | `str` | Form, Optional | The default name that will be used when sending outbound emails in this conversation. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ServiceConversation`](../../doc/models/service-conversation.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

friendly_name = 'friendly_name'

unique_name = 'unique_name'

attributes = '{ "topic": "feedback" }'

messaging_service_sid = 'MGaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

date_created = dateutil.parser.parse('12/16/2015 22:18:37')

date_updated = dateutil.parser.parse('12/16/2015 22:18:38')

state = ServiceConversationState.INACTIVE

timers_inactive = 'PT1M'

timers_closed = 'PT10M'

result = conversations_v_1_conversation_api.create_service_conversation(
    chat_service_sid,
    friendly_name=friendly_name,
    unique_name=unique_name,
    attributes=attributes,
    messaging_service_sid=messaging_service_sid,
    date_created=date_created,
    date_updated=date_updated,
    state=state,
    timers_inactive=timers_inactive,
    timers_closed=timers_closed
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# List Service Conversation

Retrieve a list of conversations in your service

```python
def list_service_conversation(self,
                             chat_service_sid,
                             start_date=None,
                             end_date=None,
                             state=None,
                             page_size=None,
                             page=None,
                             page_token=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Conversation resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `start_date` | `str` | Query, Optional | Specifies the beginning of the date range for filtering Conversations based on their creation date. Conversations that were created on or after this date will be included in the results. The date must be in ISO8601 format, specifically starting at the beginning of the specified date (YYYY-MM-DDT00:00:00Z), for precise filtering. This parameter can be combined with other filters. If this filter is used, the returned list is sorted by latest conversation creation date in descending order. |
| `end_date` | `str` | Query, Optional | Defines the end of the date range for filtering conversations by their creation date. Only conversations that were created on or before this date will appear in the results.  The date must be in ISO8601 format, specifically capturing up to the end of the specified date (YYYY-MM-DDT23:59:59Z), to ensure that conversations from the entire end day are included. This parameter can be combined with other filters. If this filter is used, the returned list is sorted by latest conversation creation date in descending order. |
| `state` | [`ServiceConversationState`](../../doc/models/service-conversation-state.md) | Query, Optional | State for sorting and filtering list of Conversations. Can be `active`, `inactive` or `closed` |
| `page_size` | `int` | Query, Optional | How many resources to return in each list page. The default is 50, and the maximum is 100.<br><br>**Constraints**: `>= 1`, `<= 100` |
| `page` | `int` | Query, Optional | The page index. This value is simply for client state.<br><br>**Constraints**: `>= 0` |
| `page_token` | `str` | Query, Optional | The page token. This is provided by the API. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ListServiceConversationResponse`](../../doc/models/list-service-conversation-response.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

result = conversations_v_1_conversation_api.list_service_conversation(chat_service_sid)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Update Service Conversation

Update an existing conversation in your service

```python
def update_service_conversation(self,
                               chat_service_sid,
                               sid,
                               x_twilio_webhook_enabled=None,
                               friendly_name=None,
                               date_created=None,
                               date_updated=None,
                               attributes=None,
                               messaging_service_sid=None,
                               state=None,
                               timers_inactive=None,
                               timers_closed=None,
                               unique_name=None,
                               bindings_email_address=None,
                               bindings_email_name=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Conversation resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `sid` | `str` | Template, Required | A 34 character string that uniquely identifies this resource. Can also be the `unique_name` of the Conversation. |
| `x_twilio_webhook_enabled` | [`ChannelWebhookEnabledType`](../../doc/models/channel-webhook-enabled-type.md) | Header, Optional | The X-Twilio-Webhook-Enabled HTTP request header |
| `friendly_name` | `str` | Form, Optional | The human-readable name of this conversation, limited to 256 characters. Optional. |
| `date_created` | `datetime` | Form, Optional | The date that this resource was created. |
| `date_updated` | `datetime` | Form, Optional | The date that this resource was last updated. |
| `attributes` | `str` | Form, Optional | An optional string metadata field you can use to store any data you wish. The string value must contain structurally valid JSON if specified.  **Note** that if the attributes are not set "{}" will be returned. |
| `messaging_service_sid` | `str` | Form, Optional | The unique ID of the [Messaging Service](https://www.twilio.com/docs/messaging/api/service-resource) this conversation belongs to.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^MG[0-9a-fA-F]{32}$` |
| `state` | [`ServiceConversationState`](../../doc/models/service-conversation-state.md) | Form, Optional | Current state of this conversation. Can be either `initializing`, `active`, `inactive` or `closed` and defaults to `active` |
| `timers_inactive` | `str` | Form, Optional | ISO8601 duration when conversation will be switched to `inactive` state. Minimum value for this timer is 1 minute. |
| `timers_closed` | `str` | Form, Optional | ISO8601 duration when conversation will be switched to `closed` state. Minimum value for this timer is 10 minutes. |
| `unique_name` | `str` | Form, Optional | An application-defined string that uniquely identifies the resource. It can be used to address the resource in place of the resource's `sid` in the URL. |
| `bindings_email_address` | `str` | Form, Optional | The default email address that will be used when sending outbound emails in this conversation. |
| `bindings_email_name` | `str` | Form, Optional | The default name that will be used when sending outbound emails in this conversation. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ServiceConversation`](../../doc/models/service-conversation.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

sid = 'Sid8'

friendly_name = 'friendly_name'

date_created = dateutil.parser.parse('12/16/2015 22:18:37')

date_updated = dateutil.parser.parse('12/16/2015 22:18:38')

attributes = '{ "topic": "feedback" }'

messaging_service_sid = 'MGaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaab'

state = ServiceConversationState.INACTIVE

timers_inactive = 'PT1M'

timers_closed = 'PT10M'

unique_name = 'unique_name'

result = conversations_v_1_conversation_api.update_service_conversation(
    chat_service_sid,
    sid,
    friendly_name=friendly_name,
    date_created=date_created,
    date_updated=date_updated,
    attributes=attributes,
    messaging_service_sid=messaging_service_sid,
    state=state,
    timers_inactive=timers_inactive,
    timers_closed=timers_closed,
    unique_name=unique_name
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Delete Service Conversation

Remove a conversation from your service

```python
def delete_service_conversation(self,
                               chat_service_sid,
                               sid,
                               x_twilio_webhook_enabled=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Conversation resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `sid` | `str` | Template, Required | A 34 character string that uniquely identifies this resource. Can also be the `unique_name` of the Conversation. |
| `x_twilio_webhook_enabled` | [`ChannelWebhookEnabledType`](../../doc/models/channel-webhook-enabled-type.md) | Header, Optional | The X-Twilio-Webhook-Enabled HTTP request header |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

sid = 'Sid8'

result = conversations_v_1_conversation_api.delete_service_conversation(
    chat_service_sid,
    sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Fetch Service Conversation

Fetch a conversation from your service

```python
def fetch_service_conversation(self,
                              chat_service_sid,
                              sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Conversation resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `sid` | `str` | Template, Required | A 34 character string that uniquely identifies this resource. Can also be the `unique_name` of the Conversation. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ServiceConversation`](../../doc/models/service-conversation.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

sid = 'Sid8'

result = conversations_v_1_conversation_api.fetch_service_conversation(
    chat_service_sid,
    sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

