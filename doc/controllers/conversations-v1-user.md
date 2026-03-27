# Conversations V1 User

```python
conversations_v_1_user_api = client.conversations_v_1_user
```

## Class Name

`ConversationsV1UserApi`

## Methods

* [Create Service User](../../doc/controllers/conversations-v1-user.md#create-service-user)
* [List Service User](../../doc/controllers/conversations-v1-user.md#list-service-user)
* [Update Service User](../../doc/controllers/conversations-v1-user.md#update-service-user)
* [Delete Service User](../../doc/controllers/conversations-v1-user.md#delete-service-user)
* [Fetch Service User](../../doc/controllers/conversations-v1-user.md#fetch-service-user)
* [Create User](../../doc/controllers/conversations-v1-user.md#create-user)
* [List User](../../doc/controllers/conversations-v1-user.md#list-user)
* [Update User](../../doc/controllers/conversations-v1-user.md#update-user)
* [Delete User](../../doc/controllers/conversations-v1-user.md#delete-user)
* [Fetch User](../../doc/controllers/conversations-v1-user.md#fetch-user)


# Create Service User

Add a new conversation user to your service

```python
def create_service_user(self,
                       chat_service_sid,
                       identity,
                       x_twilio_webhook_enabled=None,
                       friendly_name=None,
                       attributes=None,
                       role_sid=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the User resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `identity` | `str` | Form, Required | The application-defined string that uniquely identifies the resource's User within the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource). This value is often a username or an email address, and is case-sensitive. |
| `x_twilio_webhook_enabled` | [`ChannelWebhookEnabledType`](../../doc/models/channel-webhook-enabled-type.md) | Header, Optional | The X-Twilio-Webhook-Enabled HTTP request header |
| `friendly_name` | `str` | Form, Optional | The string that you assigned to describe the resource. |
| `attributes` | `str` | Form, Optional | The JSON Object string that stores application-specific data. If attributes have not been set, `{}` is returned. |
| `role_sid` | `str` | Form, Optional | The SID of a service-level [Role](https://www.twilio.com/docs/conversations/api/role-resource) to assign to the user.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^RL[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ServiceUser`](../../doc/models/service-user.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

identity = 'admin'

friendly_name = 'name'

attributes = '{ "duty": "tech" }'

role_sid = 'RLaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

result = conversations_v_1_user_api.create_service_user(
    chat_service_sid,
    identity,
    friendly_name=friendly_name,
    attributes=attributes,
    role_sid=role_sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "sid": "USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "chat_service_sid": "ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "role_sid": "RLaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "identity": "admin",
  "friendly_name": "name",
  "attributes": "{ \"duty\": \"tech\" }",
  "is_online": true,
  "is_notifiable": null,
  "date_created": "2019-12-16T22:18:37Z",
  "date_updated": "2019-12-16T22:18:38Z",
  "url": "https://conversations.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Users/USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "links": {
    "user_conversations": "https://conversations.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Users/USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Conversations"
  }
}
```


# List Service User

Retrieve a list of all conversation users in your service

```python
def list_service_user(self,
                     chat_service_sid,
                     page_size=None,
                     page=None,
                     page_token=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) to read the User resources from.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `page_size` | `int` | Query, Optional | How many resources to return in each list page. The default is 50, and the maximum is 50.<br><br>**Constraints**: `>= 1`, `<= 50` |
| `page` | `int` | Query, Optional | The page index. This value is simply for client state.<br><br>**Constraints**: `>= 0` |
| `page_token` | `str` | Query, Optional | The page token. This is provided by the API. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ListServiceUserResponse`](../../doc/models/list-service-user-response.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

result = conversations_v_1_user_api.list_service_user(chat_service_sid)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "meta": {
    "page": 0,
    "page_size": 50,
    "first_page_url": "https://conversations.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Users?PageSize=50&Page=0",
    "previous_page_url": null,
    "url": "https://conversations.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Users?PageSize=50&Page=0",
    "next_page_url": null,
    "key": "users"
  },
  "users": [
    {
      "sid": "USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "chat_service_sid": "ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "role_sid": "RLaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "identity": "admin",
      "friendly_name": "name",
      "attributes": "{ \"duty\": \"tech\" }",
      "is_online": true,
      "is_notifiable": null,
      "date_created": "2019-12-16T22:18:37Z",
      "date_updated": "2019-12-16T22:18:38Z",
      "url": "https://conversations.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Users/USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "links": {
        "user_conversations": "https://conversations.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Users/USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Conversations"
      }
    },
    {
      "sid": "USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "chat_service_sid": "ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "role_sid": "RLaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "identity": "agent0034",
      "friendly_name": "John from customs",
      "attributes": "{ \"duty\": \"agent\" }",
      "is_online": false,
      "is_notifiable": null,
      "date_created": "2020-03-24T20:38:21Z",
      "date_updated": "2020-03-24T20:38:21Z",
      "url": "https://conversations.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Users/USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "links": {
        "user_conversations": "https://conversations.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Users/USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Conversations"
      }
    }
  ]
}
```


# Update Service User

Update an existing conversation user in your service

```python
def update_service_user(self,
                       chat_service_sid,
                       sid,
                       x_twilio_webhook_enabled=None,
                       friendly_name=None,
                       attributes=None,
                       role_sid=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the User resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `sid` | `str` | Template, Required | The SID of the User resource to update. This value can be either the `sid` or the `identity` of the User resource to update. |
| `x_twilio_webhook_enabled` | [`ChannelWebhookEnabledType`](../../doc/models/channel-webhook-enabled-type.md) | Header, Optional | The X-Twilio-Webhook-Enabled HTTP request header |
| `friendly_name` | `str` | Form, Optional | The string that you assigned to describe the resource. |
| `attributes` | `str` | Form, Optional | The JSON Object string that stores application-specific data. If attributes have not been set, `{}` is returned. |
| `role_sid` | `str` | Form, Optional | The SID of a service-level [Role](https://www.twilio.com/docs/conversations/api/role-resource) to assign to the user.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^RL[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ServiceUser`](../../doc/models/service-user.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

sid = 'Sid8'

friendly_name = 'new name'

attributes = '{ "duty": "tech", "team": "internals" }'

role_sid = 'RLaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

result = conversations_v_1_user_api.update_service_user(
    chat_service_sid,
    sid,
    friendly_name=friendly_name,
    attributes=attributes,
    role_sid=role_sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "sid": "USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "chat_service_sid": "ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "role_sid": "RLaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "identity": "admin",
  "friendly_name": "new name",
  "attributes": "{ \"duty\": \"tech\", \"team\": \"internals\" }",
  "is_online": true,
  "is_notifiable": null,
  "date_created": "2019-12-16T22:18:37Z",
  "date_updated": "2019-12-16T22:18:38Z",
  "url": "https://conversations.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Users/USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "links": {
    "user_conversations": "https://conversations.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Users/USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Conversations"
  }
}
```


# Delete Service User

Remove a conversation user from your service

```python
def delete_service_user(self,
                       chat_service_sid,
                       sid,
                       x_twilio_webhook_enabled=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) to delete the User resource from.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `sid` | `str` | Template, Required | The SID of the User resource to delete. This value can be either the `sid` or the `identity` of the User resource to delete. |
| `x_twilio_webhook_enabled` | [`ChannelWebhookEnabledType`](../../doc/models/channel-webhook-enabled-type.md) | Header, Optional | The X-Twilio-Webhook-Enabled HTTP request header |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

sid = 'Sid8'

result = conversations_v_1_user_api.delete_service_user(
    chat_service_sid,
    sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Fetch Service User

Fetch a conversation user from your service

```python
def fetch_service_user(self,
                      chat_service_sid,
                      sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) to fetch the User resource from.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `sid` | `str` | Template, Required | The SID of the User resource to fetch. This value can be either the `sid` or the `identity` of the User resource to fetch. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ServiceUser`](../../doc/models/service-user.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

sid = 'Sid8'

result = conversations_v_1_user_api.fetch_service_user(
    chat_service_sid,
    sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "sid": "USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "chat_service_sid": "ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "role_sid": "RLaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "identity": "admin",
  "friendly_name": "name",
  "attributes": "{ \"duty\": \"tech\" }",
  "is_online": true,
  "is_notifiable": null,
  "date_created": "2019-12-16T22:18:37Z",
  "date_updated": "2019-12-16T22:18:38Z",
  "url": "https://conversations.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Users/USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "links": {
    "user_conversations": "https://conversations.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Users/USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Conversations"
  }
}
```


# Create User

Add a new conversation user to your account's default service

```python
def create_user(self,
               identity,
               x_twilio_webhook_enabled=None,
               friendly_name=None,
               attributes=None,
               role_sid=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `identity` | `str` | Form, Required | The application-defined string that uniquely identifies the resource's User within the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource). This value is often a username or an email address, and is case-sensitive. |
| `x_twilio_webhook_enabled` | [`ChannelWebhookEnabledType`](../../doc/models/channel-webhook-enabled-type.md) | Header, Optional | The X-Twilio-Webhook-Enabled HTTP request header |
| `friendly_name` | `str` | Form, Optional | The string that you assigned to describe the resource. |
| `attributes` | `str` | Form, Optional | The JSON Object string that stores application-specific data. If attributes have not been set, `{}` is returned. |
| `role_sid` | `str` | Form, Optional | The SID of a service-level [Role](https://www.twilio.com/docs/conversations/api/role-resource) to assign to the user.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^RL[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`User`](../../doc/models/user.md).

## Example Usage

```python
identity = 'admin'

friendly_name = 'name'

attributes = '{ "duty": "tech" }'

role_sid = 'RLaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

result = conversations_v_1_user_api.create_user(
    identity,
    friendly_name=friendly_name,
    attributes=attributes,
    role_sid=role_sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "sid": "USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "chat_service_sid": "ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "role_sid": "RLaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "identity": "admin",
  "friendly_name": "name",
  "attributes": "{ \"duty\": \"tech\" }",
  "is_online": true,
  "is_notifiable": null,
  "date_created": "2019-12-16T22:18:37Z",
  "date_updated": "2019-12-16T22:18:38Z",
  "url": "https://conversations.twilio.com/v1/Users/USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "links": {
    "user_conversations": "https://conversations.twilio.com/v1/Users/USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Conversations"
  }
}
```


# List User

Retrieve a list of all conversation users in your account's default service

```python
def list_user(self,
             page_size=None,
             page=None,
             page_token=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `page_size` | `int` | Query, Optional | How many resources to return in each list page. The default is 50, and the maximum is 50.<br><br>**Constraints**: `>= 1`, `<= 50` |
| `page` | `int` | Query, Optional | The page index. This value is simply for client state.<br><br>**Constraints**: `>= 0` |
| `page_token` | `str` | Query, Optional | The page token. This is provided by the API. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ListUserResponse`](../../doc/models/list-user-response.md).

## Example Usage

```python
result = conversations_v_1_user_api.list_user()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "meta": {
    "page": 0,
    "page_size": 50,
    "first_page_url": "https://conversations.twilio.com/v1/Users?PageSize=50&Page=0",
    "previous_page_url": null,
    "url": "https://conversations.twilio.com/v1/Users?PageSize=50&Page=0",
    "next_page_url": null,
    "key": "users"
  },
  "users": [
    {
      "sid": "USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "chat_service_sid": "ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "role_sid": "RLaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "identity": "admin",
      "friendly_name": "name",
      "attributes": "{ \"duty\": \"tech\" }",
      "is_online": true,
      "is_notifiable": null,
      "date_created": "2019-12-16T22:18:37Z",
      "date_updated": "2019-12-16T22:18:38Z",
      "url": "https://conversations.twilio.com/v1/Users/USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "links": {
        "user_conversations": "https://conversations.twilio.com/v1/Users/USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Conversations"
      }
    },
    {
      "sid": "USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "chat_service_sid": "ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "role_sid": "RLaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "identity": "agent0034",
      "friendly_name": "John from customs",
      "attributes": "{ \"duty\": \"agent\" }",
      "is_online": false,
      "is_notifiable": null,
      "date_created": "2020-03-24T20:38:21Z",
      "date_updated": "2020-03-24T20:38:21Z",
      "url": "https://conversations.twilio.com/v1/Users/USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "links": {
        "user_conversations": "https://conversations.twilio.com/v1/Users/USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Conversations"
      }
    }
  ]
}
```


# Update User

Update an existing conversation user in your account's default service

```python
def update_user(self,
               sid,
               x_twilio_webhook_enabled=None,
               friendly_name=None,
               attributes=None,
               role_sid=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sid` | `str` | Template, Required | The SID of the User resource to update. This value can be either the `sid` or the `identity` of the User resource to update. |
| `x_twilio_webhook_enabled` | [`ChannelWebhookEnabledType`](../../doc/models/channel-webhook-enabled-type.md) | Header, Optional | The X-Twilio-Webhook-Enabled HTTP request header |
| `friendly_name` | `str` | Form, Optional | The string that you assigned to describe the resource. |
| `attributes` | `str` | Form, Optional | The JSON Object string that stores application-specific data. If attributes have not been set, `{}` is returned. |
| `role_sid` | `str` | Form, Optional | The SID of a service-level [Role](https://www.twilio.com/docs/conversations/api/role-resource) to assign to the user.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^RL[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`User`](../../doc/models/user.md).

## Example Usage

```python
sid = 'Sid8'

friendly_name = 'new name'

attributes = '{ "duty": "tech", "team": "internals" }'

role_sid = 'RLaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

result = conversations_v_1_user_api.update_user(
    sid,
    friendly_name=friendly_name,
    attributes=attributes,
    role_sid=role_sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "sid": "USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "chat_service_sid": "ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "role_sid": "RLaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "identity": "admin",
  "friendly_name": "new name",
  "attributes": "{ \"duty\": \"tech\", \"team\": \"internals\" }",
  "is_online": true,
  "is_notifiable": null,
  "date_created": "2019-12-16T22:18:37Z",
  "date_updated": "2019-12-16T22:18:38Z",
  "url": "https://conversations.twilio.com/v1/Users/USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "links": {
    "user_conversations": "https://conversations.twilio.com/v1/Users/USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Conversations"
  }
}
```


# Delete User

Remove a conversation user from your account's default service

```python
def delete_user(self,
               sid,
               x_twilio_webhook_enabled=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sid` | `str` | Template, Required | The SID of the User resource to delete. This value can be either the `sid` or the `identity` of the User resource to delete. |
| `x_twilio_webhook_enabled` | [`ChannelWebhookEnabledType`](../../doc/models/channel-webhook-enabled-type.md) | Header, Optional | The X-Twilio-Webhook-Enabled HTTP request header |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```python
sid = 'Sid8'

result = conversations_v_1_user_api.delete_user(sid)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Fetch User

Fetch a conversation user from your account's default service

```python
def fetch_user(self,
              sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sid` | `str` | Template, Required | The SID of the User resource to fetch. This value can be either the `sid` or the `identity` of the User resource to fetch. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`User`](../../doc/models/user.md).

## Example Usage

```python
sid = 'Sid8'

result = conversations_v_1_user_api.fetch_user(sid)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "sid": "USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "chat_service_sid": "ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "role_sid": "RLaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "identity": "admin",
  "friendly_name": "name",
  "attributes": "{ \"duty\": \"tech\" }",
  "is_online": true,
  "is_notifiable": null,
  "date_created": "2019-12-16T22:18:37Z",
  "date_updated": "2019-12-16T22:18:38Z",
  "url": "https://conversations.twilio.com/v1/Users/USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "links": {
    "user_conversations": "https://conversations.twilio.com/v1/Users/USaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Conversations"
  }
}
```

