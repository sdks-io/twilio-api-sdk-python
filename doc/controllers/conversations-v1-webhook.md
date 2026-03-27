# Conversations V1 Webhook

```python
conversations_v_1_webhook_api = client.conversations_v_1_webhook
```

## Class Name

`ConversationsV1WebhookApi`

## Methods

* [Fetch Configuration Webhook](../../doc/controllers/conversations-v1-webhook.md#fetch-configuration-webhook)
* [Update Configuration Webhook](../../doc/controllers/conversations-v1-webhook.md#update-configuration-webhook)
* [List Conversation Scoped Webhook](../../doc/controllers/conversations-v1-webhook.md#list-conversation-scoped-webhook)
* [Create Conversation Scoped Webhook](../../doc/controllers/conversations-v1-webhook.md#create-conversation-scoped-webhook)
* [Fetch Conversation Scoped Webhook](../../doc/controllers/conversations-v1-webhook.md#fetch-conversation-scoped-webhook)
* [Update Conversation Scoped Webhook](../../doc/controllers/conversations-v1-webhook.md#update-conversation-scoped-webhook)
* [Delete Conversation Scoped Webhook](../../doc/controllers/conversations-v1-webhook.md#delete-conversation-scoped-webhook)
* [Create Service Conversation Scoped Webhook](../../doc/controllers/conversations-v1-webhook.md#create-service-conversation-scoped-webhook)
* [List Service Conversation Scoped Webhook](../../doc/controllers/conversations-v1-webhook.md#list-service-conversation-scoped-webhook)
* [Update Service Conversation Scoped Webhook](../../doc/controllers/conversations-v1-webhook.md#update-service-conversation-scoped-webhook)
* [Delete Service Conversation Scoped Webhook](../../doc/controllers/conversations-v1-webhook.md#delete-service-conversation-scoped-webhook)
* [Fetch Service Conversation Scoped Webhook](../../doc/controllers/conversations-v1-webhook.md#fetch-service-conversation-scoped-webhook)
* [Update Service Webhook Configuration](../../doc/controllers/conversations-v1-webhook.md#update-service-webhook-configuration)
* [Fetch Service Webhook Configuration](../../doc/controllers/conversations-v1-webhook.md#fetch-service-webhook-configuration)


# Fetch Configuration Webhook

A Webhook resource manages a service-level set of callback URLs and their configuration for receiving all conversation events.

```python
def fetch_configuration_webhook(self)
```

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConfigurationWebhook`](../../doc/models/configuration-webhook.md).

## Example Usage

```python
result = conversations_v_1_webhook_api.fetch_configuration_webhook()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "pre_webhook_url": "https://example.com/pre",
  "post_webhook_url": "https://example.com/post",
  "method": "GET",
  "filters": [
    "onMessageSend",
    "onConversationUpdated"
  ],
  "target": "webhook",
  "url": "https://conversations.twilio.com/v1/Configuration/Webhooks"
}
```


# Update Configuration Webhook

A Webhook resource manages a service-level set of callback URLs and their configuration for receiving all conversation events.

```python
def update_configuration_webhook(self,
                                method=None,
                                filters=None,
                                pre_webhook_url=None,
                                post_webhook_url=None,
                                target=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `method` | `str` | Form, Optional | The HTTP method to be used when sending a webhook request. |
| `filters` | `List[str]` | Form, Optional | The list of webhook event triggers that are enabled for this Service: `onMessageAdded`, `onMessageUpdated`, `onMessageRemoved`, `onMessageAdd`, `onMessageUpdate`, `onMessageRemove`, `onConversationUpdated`, `onConversationRemoved`, `onConversationAdd`, `onConversationAdded`, `onConversationRemove`, `onConversationUpdate`, `onConversationStateUpdated`, `onParticipantAdded`, `onParticipantUpdated`, `onParticipantRemoved`, `onParticipantAdd`, `onParticipantRemove`, `onParticipantUpdate`, `onDeliveryUpdated`, `onUserAdded`, `onUserUpdate`, `onUserUpdated` |
| `pre_webhook_url` | `str` | Form, Optional | The absolute url the pre-event webhook request should be sent to. |
| `post_webhook_url` | `str` | Form, Optional | The absolute url the post-event webhook request should be sent to. |
| `target` | [`ConfigurationWebhookTarget`](../../doc/models/configuration-webhook-target.md) | Form, Optional | The routing target of the webhook. Can be ordinary or route internally to Flex |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConfigurationWebhook`](../../doc/models/configuration-webhook.md).

## Example Usage

```python
method = 'GET'

filters = [
    'onConversationUpdated'
]

pre_webhook_url = 'https://example.com/pre'

post_webhook_url = 'https://example.com/post'

target = ConfigurationWebhookTarget.WEBHOOK

result = conversations_v_1_webhook_api.update_configuration_webhook(
    method=method,
    filters=filters,
    pre_webhook_url=pre_webhook_url,
    post_webhook_url=post_webhook_url,
    target=target
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "pre_webhook_url": "https://example.com/pre",
  "post_webhook_url": "http://example.com/post",
  "method": "GET",
  "filters": [
    "onConversationUpdated"
  ],
  "target": "webhook",
  "url": "https://conversations.twilio.com/v1/Configuration/Webhooks"
}
```


# List Conversation Scoped Webhook

Retrieve a list of all webhooks scoped to the conversation

```python
def list_conversation_scoped_webhook(self,
                                    conversation_sid,
                                    page_size=None,
                                    page=None,
                                    page_token=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for this webhook. |
| `page_size` | `int` | Query, Optional | How many resources to return in each list page. The default is 5, and the maximum is 5.<br><br>**Constraints**: `>= 1`, `<= 5` |
| `page` | `int` | Query, Optional | The page index. This value is simply for client state.<br><br>**Constraints**: `>= 0` |
| `page_token` | `str` | Query, Optional | The page token. This is provided by the API. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ListConversationScopedWebhookResponse`](../../doc/models/list-conversation-scoped-webhook-response.md).

## Example Usage

```python
conversation_sid = 'ConversationSid0'

result = conversations_v_1_webhook_api.list_conversation_scoped_webhook(conversation_sid)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Create Conversation Scoped Webhook

Create a new webhook scoped to the conversation

```python
def create_conversation_scoped_webhook(self,
                                      conversation_sid,
                                      target,
                                      configuration_url=None,
                                      configuration_method=None,
                                      configuration_filters=None,
                                      configuration_triggers=None,
                                      configuration_flow_sid=None,
                                      configuration_replay_after=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for this webhook. |
| `target` | [`ConversationScopedWebhookTarget`](../../doc/models/conversation-scoped-webhook-target.md) | Form, Required | The target of this webhook: `webhook`, `studio`, `trigger` |
| `configuration_url` | `str` | Form, Optional | The absolute url the webhook request should be sent to. |
| `configuration_method` | [`ConversationScopedWebhookMethod`](../../doc/models/conversation-scoped-webhook-method.md) | Form, Optional | - |
| `configuration_filters` | `List[str]` | Form, Optional | The list of events, firing webhook event for this Conversation. |
| `configuration_triggers` | `List[str]` | Form, Optional | The list of keywords, firing webhook event for this Conversation. |
| `configuration_flow_sid` | `str` | Form, Optional | The studio flow SID, where the webhook should be sent to.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^FW[0-9a-fA-F]{32}$` |
| `configuration_replay_after` | `int` | Form, Optional | The message index for which and it's successors the webhook will be replayed. Not set by default |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConversationScopedWebhook`](../../doc/models/conversation-scoped-webhook.md).

## Example Usage

```python
conversation_sid = 'ConversationSid0'

target = ConversationScopedWebhookTarget.WEBHOOK

configuration_url = 'https://example.com'

configuration_method = ConversationScopedWebhookMethod.GET

configuration_filters = [
    'onMessageSent',
    'onConversationDestroyed'
]

configuration_replay_after = 7

result = conversations_v_1_webhook_api.create_conversation_scoped_webhook(
    conversation_sid,
    target,
    configuration_url=configuration_url,
    configuration_method=configuration_method,
    configuration_filters=configuration_filters,
    configuration_replay_after=configuration_replay_after
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Fetch Conversation Scoped Webhook

Fetch the configuration of a conversation-scoped webhook

```python
def fetch_conversation_scoped_webhook(self,
                                     conversation_sid,
                                     sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for this webhook. |
| `sid` | `str` | Template, Required | A 34 character string that uniquely identifies this resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WH[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConversationScopedWebhook`](../../doc/models/conversation-scoped-webhook.md).

## Example Usage

```python
conversation_sid = 'ConversationSid0'

sid = 'Sid8'

result = conversations_v_1_webhook_api.fetch_conversation_scoped_webhook(
    conversation_sid,
    sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Update Conversation Scoped Webhook

Update an existing conversation-scoped webhook

```python
def update_conversation_scoped_webhook(self,
                                      conversation_sid,
                                      sid,
                                      configuration_url=None,
                                      configuration_method=None,
                                      configuration_filters=None,
                                      configuration_triggers=None,
                                      configuration_flow_sid=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for this webhook. |
| `sid` | `str` | Template, Required | A 34 character string that uniquely identifies this resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WH[0-9a-fA-F]{32}$` |
| `configuration_url` | `str` | Form, Optional | The absolute url the webhook request should be sent to. |
| `configuration_method` | [`ConversationScopedWebhookMethod`](../../doc/models/conversation-scoped-webhook-method.md) | Form, Optional | - |
| `configuration_filters` | `List[str]` | Form, Optional | The list of events, firing webhook event for this Conversation. |
| `configuration_triggers` | `List[str]` | Form, Optional | The list of keywords, firing webhook event for this Conversation. |
| `configuration_flow_sid` | `str` | Form, Optional | The studio flow SID, where the webhook should be sent to.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^FW[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConversationScopedWebhook`](../../doc/models/conversation-scoped-webhook.md).

## Example Usage

```python
conversation_sid = 'ConversationSid0'

sid = 'Sid8'

configuration_url = 'https://example.com'

configuration_method = ConversationScopedWebhookMethod.POST

configuration_triggers = [
    'keyword1',
    'keyword2'
]

result = conversations_v_1_webhook_api.update_conversation_scoped_webhook(
    conversation_sid,
    sid,
    configuration_url=configuration_url,
    configuration_method=configuration_method,
    configuration_triggers=configuration_triggers
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Delete Conversation Scoped Webhook

Remove an existing webhook scoped to the conversation

```python
def delete_conversation_scoped_webhook(self,
                                      conversation_sid,
                                      sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for this webhook. |
| `sid` | `str` | Template, Required | A 34 character string that uniquely identifies this resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WH[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```python
conversation_sid = 'ConversationSid0'

sid = 'Sid8'

result = conversations_v_1_webhook_api.delete_conversation_scoped_webhook(
    conversation_sid,
    sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Create Service Conversation Scoped Webhook

Create a new webhook scoped to the conversation in a specific service

```python
def create_service_conversation_scoped_webhook(self,
                                              chat_service_sid,
                                              conversation_sid,
                                              target,
                                              configuration_url=None,
                                              configuration_method=None,
                                              configuration_filters=None,
                                              configuration_triggers=None,
                                              configuration_flow_sid=None,
                                              configuration_replay_after=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Participant resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for this webhook. |
| `target` | [`ServiceConversationScopedWebhookTarget`](../../doc/models/service-conversation-scoped-webhook-target.md) | Form, Required | The target of this webhook: `webhook`, `studio`, `trigger` |
| `configuration_url` | `str` | Form, Optional | The absolute url the webhook request should be sent to. |
| `configuration_method` | [`ServiceConversationScopedWebhookMethod`](../../doc/models/service-conversation-scoped-webhook-method.md) | Form, Optional | - |
| `configuration_filters` | `List[str]` | Form, Optional | The list of events, firing webhook event for this Conversation. |
| `configuration_triggers` | `List[str]` | Form, Optional | The list of keywords, firing webhook event for this Conversation. |
| `configuration_flow_sid` | `str` | Form, Optional | The studio flow SID, where the webhook should be sent to.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^FW[0-9a-fA-F]{32}$` |
| `configuration_replay_after` | `int` | Form, Optional | The message index for which and it's successors the webhook will be replayed. Not set by default |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ServiceConversationScopedWebhook`](../../doc/models/service-conversation-scoped-webhook.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

conversation_sid = 'ConversationSid0'

target = ServiceConversationScopedWebhookTarget.WEBHOOK

configuration_url = 'https://example.com'

configuration_method = ServiceConversationScopedWebhookMethod.GET

configuration_filters = [
    'onMessageSent',
    'onConversationDestroyed'
]

configuration_replay_after = 7

result = conversations_v_1_webhook_api.create_service_conversation_scoped_webhook(
    chat_service_sid,
    conversation_sid,
    target,
    configuration_url=configuration_url,
    configuration_method=configuration_method,
    configuration_filters=configuration_filters,
    configuration_replay_after=configuration_replay_after
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# List Service Conversation Scoped Webhook

Retrieve a list of all webhooks scoped to the conversation

```python
def list_service_conversation_scoped_webhook(self,
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
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for this webhook. |
| `page_size` | `int` | Query, Optional | How many resources to return in each list page. The default is 5, and the maximum is 5.<br><br>**Constraints**: `>= 1`, `<= 5` |
| `page` | `int` | Query, Optional | The page index. This value is simply for client state.<br><br>**Constraints**: `>= 0` |
| `page_token` | `str` | Query, Optional | The page token. This is provided by the API. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ListServiceConversationScopedWebhookResponse`](../../doc/models/list-service-conversation-scoped-webhook-response.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

conversation_sid = 'ConversationSid0'

result = conversations_v_1_webhook_api.list_service_conversation_scoped_webhook(
    chat_service_sid,
    conversation_sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Update Service Conversation Scoped Webhook

Update an existing conversation-scoped webhook

```python
def update_service_conversation_scoped_webhook(self,
                                              chat_service_sid,
                                              conversation_sid,
                                              sid,
                                              configuration_url=None,
                                              configuration_method=None,
                                              configuration_filters=None,
                                              configuration_triggers=None,
                                              configuration_flow_sid=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Participant resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for this webhook. |
| `sid` | `str` | Template, Required | A 34 character string that uniquely identifies this resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WH[0-9a-fA-F]{32}$` |
| `configuration_url` | `str` | Form, Optional | The absolute url the webhook request should be sent to. |
| `configuration_method` | [`ServiceConversationScopedWebhookMethod`](../../doc/models/service-conversation-scoped-webhook-method.md) | Form, Optional | - |
| `configuration_filters` | `List[str]` | Form, Optional | The list of events, firing webhook event for this Conversation. |
| `configuration_triggers` | `List[str]` | Form, Optional | The list of keywords, firing webhook event for this Conversation. |
| `configuration_flow_sid` | `str` | Form, Optional | The studio flow SID, where the webhook should be sent to.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^FW[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ServiceConversationScopedWebhook`](../../doc/models/service-conversation-scoped-webhook.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

conversation_sid = 'ConversationSid0'

sid = 'Sid8'

configuration_url = 'https://example.com'

configuration_method = ServiceConversationScopedWebhookMethod.POST

configuration_triggers = [
    'keyword1',
    'keyword2'
]

result = conversations_v_1_webhook_api.update_service_conversation_scoped_webhook(
    chat_service_sid,
    conversation_sid,
    sid,
    configuration_url=configuration_url,
    configuration_method=configuration_method,
    configuration_triggers=configuration_triggers
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Delete Service Conversation Scoped Webhook

Remove an existing webhook scoped to the conversation

```python
def delete_service_conversation_scoped_webhook(self,
                                              chat_service_sid,
                                              conversation_sid,
                                              sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Participant resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for this webhook. |
| `sid` | `str` | Template, Required | A 34 character string that uniquely identifies this resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WH[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

conversation_sid = 'ConversationSid0'

sid = 'Sid8'

result = conversations_v_1_webhook_api.delete_service_conversation_scoped_webhook(
    chat_service_sid,
    conversation_sid,
    sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Fetch Service Conversation Scoped Webhook

Fetch the configuration of a conversation-scoped webhook

```python
def fetch_service_conversation_scoped_webhook(self,
                                             chat_service_sid,
                                             conversation_sid,
                                             sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Participant resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `conversation_sid` | `str` | Template, Required | The unique ID of the [Conversation](https://www.twilio.com/docs/conversations/api/conversation-resource) for this webhook. |
| `sid` | `str` | Template, Required | A 34 character string that uniquely identifies this resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WH[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ServiceConversationScopedWebhook`](../../doc/models/service-conversation-scoped-webhook.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

conversation_sid = 'ConversationSid0'

sid = 'Sid8'

result = conversations_v_1_webhook_api.fetch_service_conversation_scoped_webhook(
    chat_service_sid,
    conversation_sid,
    sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Update Service Webhook Configuration

Update a specific Webhook.

```python
def update_service_webhook_configuration(self,
                                        chat_service_sid,
                                        pre_webhook_url=None,
                                        post_webhook_url=None,
                                        filters=None,
                                        method=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The unique ID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) this conversation belongs to.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `pre_webhook_url` | `str` | Form, Optional | The absolute url the pre-event webhook request should be sent to. |
| `post_webhook_url` | `str` | Form, Optional | The absolute url the post-event webhook request should be sent to. |
| `filters` | `List[str]` | Form, Optional | The list of events that your configured webhook targets will receive. Events not configured here will not fire. Possible values are `onParticipantAdd`, `onParticipantAdded`, `onDeliveryUpdated`, `onConversationUpdated`, `onConversationRemove`, `onParticipantRemove`, `onConversationUpdate`, `onMessageAdd`, `onMessageRemoved`, `onParticipantUpdated`, `onConversationAdded`, `onMessageAdded`, `onConversationAdd`, `onConversationRemoved`, `onParticipantUpdate`, `onMessageRemove`, `onMessageUpdated`, `onParticipantRemoved`, `onMessageUpdate` or `onConversationStateUpdated`. |
| `method` | `str` | Form, Optional | The HTTP method to be used when sending a webhook request. One of `GET` or `POST`. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ServiceWebhookConfiguration`](../../doc/models/service-webhook-configuration.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

pre_webhook_url = 'https://www.example.com/pre'

post_webhook_url = 'https://www.example.com/post'

filters = [
    'onMessageRemoved',
    'onParticipantAdded'
]

method = 'GET'

result = conversations_v_1_webhook_api.update_service_webhook_configuration(
    chat_service_sid,
    pre_webhook_url=pre_webhook_url,
    post_webhook_url=post_webhook_url,
    filters=filters,
    method=method
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "chat_service_sid": "ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "pre_webhook_url": "https://www.example.com/pre",
  "post_webhook_url": "https://www.example.com/post",
  "filters": [
    "onMessageRemoved",
    "onParticipantAdded"
  ],
  "method": "GET",
  "url": "https://conversations.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Configuration/Webhooks"
}
```


# Fetch Service Webhook Configuration

Fetch a specific service webhook configuration.

```python
def fetch_service_webhook_configuration(self,
                                       chat_service_sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The unique ID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) this conversation belongs to.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ServiceWebhookConfiguration`](../../doc/models/service-webhook-configuration.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

result = conversations_v_1_webhook_api.fetch_service_webhook_configuration(chat_service_sid)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "chat_service_sid": "ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "pre_webhook_url": "https://www.example.com/pre",
  "post_webhook_url": "https://www.example.com/post",
  "filters": [
    "onMessageRemove",
    "onParticipantAdd"
  ],
  "method": "POST",
  "url": "https://conversations.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Configuration/Webhooks"
}
```

