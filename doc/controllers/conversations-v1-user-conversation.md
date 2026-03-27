# Conversations V1 User Conversation

```python
conversations_v_1_user_conversation_api = client.conversations_v_1_user_conversation
```

## Class Name

`ConversationsV1UserConversationApi`

## Methods

* [Update Service User Conversation](../../doc/controllers/conversations-v1-user-conversation.md#update-service-user-conversation)
* [Delete Service User Conversation](../../doc/controllers/conversations-v1-user-conversation.md#delete-service-user-conversation)
* [Fetch Service User Conversation](../../doc/controllers/conversations-v1-user-conversation.md#fetch-service-user-conversation)
* [List Service User Conversation](../../doc/controllers/conversations-v1-user-conversation.md#list-service-user-conversation)
* [Update User Conversation](../../doc/controllers/conversations-v1-user-conversation.md#update-user-conversation)
* [Delete User Conversation](../../doc/controllers/conversations-v1-user-conversation.md#delete-user-conversation)
* [Fetch User Conversation](../../doc/controllers/conversations-v1-user-conversation.md#fetch-user-conversation)
* [List User Conversation](../../doc/controllers/conversations-v1-user-conversation.md#list-user-conversation)


# Update Service User Conversation

Update a specific User Conversation.

```python
def update_service_user_conversation(self,
                                    chat_service_sid,
                                    user_sid,
                                    conversation_sid,
                                    notification_level=None,
                                    last_read_timestamp=None,
                                    last_read_message_index=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Conversation resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `user_sid` | `str` | Template, Required | The unique SID identifier of the [User resource](https://www.twilio.com/docs/conversations/api/user-resource). This value can be either the `sid` or the `identity` of the User resource. |
| `conversation_sid` | `str` | Template, Required | The unique SID identifier of the Conversation. This value can be either the `sid` or the `unique_name` of the [Conversation resource](https://www.twilio.com/docs/conversations/api/conversation-resource). |
| `notification_level` | [`ServiceUserConversationNotificationLevel`](../../doc/models/service-user-conversation-notification-level.md) | Form, Optional | The Notification Level of this User Conversation. One of `default` or `muted`. |
| `last_read_timestamp` | `datetime` | Form, Optional | The date of the last message read in conversation by the user, given in ISO 8601 format. |
| `last_read_message_index` | `int` | Form, Optional | The index of the last Message in the Conversation that the Participant has read. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ServiceUserConversation`](../../doc/models/service-user-conversation.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

user_sid = 'UserSid6'

conversation_sid = 'ConversationSid0'

notification_level = ServiceUserConversationNotificationLevel.DEFAULT

last_read_timestamp = dateutil.parser.parse('07/30/2015 20:00:00')

last_read_message_index = 100

result = conversations_v_1_user_conversation_api.update_service_user_conversation(
    chat_service_sid,
    user_sid,
    conversation_sid,
    notification_level=notification_level,
    last_read_timestamp=last_read_timestamp,
    last_read_message_index=last_read_message_index
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Delete Service User Conversation

Delete a specific User Conversation.

```python
def delete_service_user_conversation(self,
                                    chat_service_sid,
                                    user_sid,
                                    conversation_sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Conversation resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `user_sid` | `str` | Template, Required | The unique SID identifier of the [User resource](https://www.twilio.com/docs/conversations/api/user-resource). This value can be either the `sid` or the `identity` of the User resource. |
| `conversation_sid` | `str` | Template, Required | The unique SID identifier of the Conversation. This value can be either the `sid` or the `unique_name` of the [Conversation resource](https://www.twilio.com/docs/conversations/api/conversation-resource). |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

user_sid = 'UserSid6'

conversation_sid = 'ConversationSid0'

result = conversations_v_1_user_conversation_api.delete_service_user_conversation(
    chat_service_sid,
    user_sid,
    conversation_sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Fetch Service User Conversation

Fetch a specific User Conversation.

```python
def fetch_service_user_conversation(self,
                                   chat_service_sid,
                                   user_sid,
                                   conversation_sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Conversation resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `user_sid` | `str` | Template, Required | The unique SID identifier of the [User resource](https://www.twilio.com/docs/conversations/api/user-resource). This value can be either the `sid` or the `identity` of the User resource. |
| `conversation_sid` | `str` | Template, Required | The unique SID identifier of the Conversation. This value can be either the `sid` or the `unique_name` of the [Conversation resource](https://www.twilio.com/docs/conversations/api/conversation-resource). |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ServiceUserConversation`](../../doc/models/service-user-conversation.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

user_sid = 'UserSid6'

conversation_sid = 'ConversationSid0'

result = conversations_v_1_user_conversation_api.fetch_service_user_conversation(
    chat_service_sid,
    user_sid,
    conversation_sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# List Service User Conversation

Retrieve a list of all User Conversations for the User.

```python
def list_service_user_conversation(self,
                                  chat_service_sid,
                                  user_sid,
                                  page_size=None,
                                  page=None,
                                  page_token=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Conversation resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `user_sid` | `str` | Template, Required | The unique SID identifier of the [User resource](https://www.twilio.com/docs/conversations/api/user-resource). This value can be either the `sid` or the `identity` of the User resource. |
| `page_size` | `int` | Query, Optional | How many resources to return in each list page. The default is 50, and the maximum is 50.<br><br>**Constraints**: `>= 1`, `<= 50` |
| `page` | `int` | Query, Optional | The page index. This value is simply for client state.<br><br>**Constraints**: `>= 0` |
| `page_token` | `str` | Query, Optional | The page token. This is provided by the API. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ListServiceUserConversationResponse`](../../doc/models/list-service-user-conversation-response.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

user_sid = 'UserSid6'

result = conversations_v_1_user_conversation_api.list_service_user_conversation(
    chat_service_sid,
    user_sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "conversations": [],
  "meta": {
    "page": 0,
    "page_size": 50,
    "first_page_url": "https://conversations.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Users/USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Conversations?PageSize=50&Page=0",
    "previous_page_url": null,
    "url": "https://conversations.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Users/USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Conversations?PageSize=50&Page=0",
    "next_page_url": null,
    "key": "conversations"
  }
}
```


# Update User Conversation

Update a specific User Conversation.

```python
def update_user_conversation(self,
                            user_sid,
                            conversation_sid,
                            notification_level=None,
                            last_read_timestamp=None,
                            last_read_message_index=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `user_sid` | `str` | Template, Required | The unique SID identifier of the [User resource](https://www.twilio.com/docs/conversations/api/user-resource). This value can be either the `sid` or the `identity` of the User resource. |
| `conversation_sid` | `str` | Template, Required | The unique SID identifier of the Conversation. This value can be either the `sid` or the `unique_name` of the [Conversation resource](https://www.twilio.com/docs/conversations/api/conversation-resource). |
| `notification_level` | [`UserConversationNotificationLevel`](../../doc/models/user-conversation-notification-level.md) | Form, Optional | The Notification Level of this User Conversation. One of `default` or `muted`. |
| `last_read_timestamp` | `datetime` | Form, Optional | The date of the last message read in conversation by the user, given in ISO 8601 format. |
| `last_read_message_index` | `int` | Form, Optional | The index of the last Message in the Conversation that the Participant has read. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`UserConversation`](../../doc/models/user-conversation.md).

## Example Usage

```python
user_sid = 'UserSid6'

conversation_sid = 'ConversationSid0'

notification_level = UserConversationNotificationLevel.DEFAULT

last_read_timestamp = dateutil.parser.parse('07/30/2015 20:00:00')

last_read_message_index = 100

result = conversations_v_1_user_conversation_api.update_user_conversation(
    user_sid,
    conversation_sid,
    notification_level=notification_level,
    last_read_timestamp=last_read_timestamp,
    last_read_message_index=last_read_message_index
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Delete User Conversation

Delete a specific User Conversation.

```python
def delete_user_conversation(self,
                            user_sid,
                            conversation_sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `user_sid` | `str` | Template, Required | The unique SID identifier of the [User resource](https://www.twilio.com/docs/conversations/api/user-resource). This value can be either the `sid` or the `identity` of the User resource. |
| `conversation_sid` | `str` | Template, Required | The unique SID identifier of the Conversation. This value can be either the `sid` or the `unique_name` of the [Conversation resource](https://www.twilio.com/docs/conversations/api/conversation-resource). |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```python
user_sid = 'UserSid6'

conversation_sid = 'ConversationSid0'

result = conversations_v_1_user_conversation_api.delete_user_conversation(
    user_sid,
    conversation_sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Fetch User Conversation

Fetch a specific User Conversation.

```python
def fetch_user_conversation(self,
                           user_sid,
                           conversation_sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `user_sid` | `str` | Template, Required | The unique SID identifier of the [User resource](https://www.twilio.com/docs/conversations/api/user-resource). This value can be either the `sid` or the `identity` of the User resource. |
| `conversation_sid` | `str` | Template, Required | The unique SID identifier of the Conversation. This value can be either the `sid` or the `unique_name` of the [Conversation resource](https://www.twilio.com/docs/conversations/api/conversation-resource). |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`UserConversation`](../../doc/models/user-conversation.md).

## Example Usage

```python
user_sid = 'UserSid6'

conversation_sid = 'ConversationSid0'

result = conversations_v_1_user_conversation_api.fetch_user_conversation(
    user_sid,
    conversation_sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# List User Conversation

Retrieve a list of all User Conversations for the User.

```python
def list_user_conversation(self,
                          user_sid,
                          page_size=None,
                          page=None,
                          page_token=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `user_sid` | `str` | Template, Required | The unique SID identifier of the [User resource](https://www.twilio.com/docs/conversations/api/user-resource). This value can be either the `sid` or the `identity` of the User resource. |
| `page_size` | `int` | Query, Optional | How many resources to return in each list page. The default is 50, and the maximum is 50.<br><br>**Constraints**: `>= 1`, `<= 50` |
| `page` | `int` | Query, Optional | The page index. This value is simply for client state.<br><br>**Constraints**: `>= 0` |
| `page_token` | `str` | Query, Optional | The page token. This is provided by the API. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ListUserConversationResponse`](../../doc/models/list-user-conversation-response.md).

## Example Usage

```python
user_sid = 'UserSid6'

result = conversations_v_1_user_conversation_api.list_user_conversation(user_sid)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "conversations": [],
  "meta": {
    "page": 0,
    "page_size": 50,
    "first_page_url": "https://conversations.twilio.com/v1/Users/USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Conversations?PageSize=50&Page=0",
    "previous_page_url": null,
    "url": "https://conversations.twilio.com/v1/Users/USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Conversations?PageSize=50&Page=0",
    "next_page_url": null,
    "key": "conversations"
  }
}
```

