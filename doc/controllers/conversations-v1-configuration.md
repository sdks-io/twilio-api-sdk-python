# Conversations V1 Configuration

```python
conversations_v_1_configuration_api = client.conversations_v_1_configuration
```

## Class Name

`ConversationsV1ConfigurationApi`

## Methods

* [Fetch Configuration](../../doc/controllers/conversations-v1-configuration.md#fetch-configuration)
* [Update Configuration](../../doc/controllers/conversations-v1-configuration.md#update-configuration)
* [Fetch Service Configuration](../../doc/controllers/conversations-v1-configuration.md#fetch-service-configuration)
* [Update Service Configuration](../../doc/controllers/conversations-v1-configuration.md#update-service-configuration)


# Fetch Configuration

Fetch the global configuration of conversations on your account

```python
def fetch_configuration(self)
```

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Configuration`](../../doc/models/configuration.md).

## Example Usage

```python
result = conversations_v_1_configuration_api.fetch_configuration()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "default_chat_service_sid": "ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "default_messaging_service_sid": "MGaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "default_inactive_timer": "PT1M",
  "default_closed_timer": "PT10M",
  "url": "https://conversations.twilio.com/v1/Configuration",
  "links": {
    "service": "https://conversations.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Configuration",
    "webhooks": "https://conversations.twilio.com/v1/Configuration/Webhooks"
  }
}
```


# Update Configuration

Update the global configuration of conversations on your account

```python
def update_configuration(self,
                        default_chat_service_sid=None,
                        default_messaging_service_sid=None,
                        default_inactive_timer=None,
                        default_closed_timer=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `default_chat_service_sid` | `str` | Form, Optional | The SID of the default [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) to use when creating a conversation.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `default_messaging_service_sid` | `str` | Form, Optional | The SID of the default [Messaging Service](https://www.twilio.com/docs/messaging/api/service-resource) to use when creating a conversation.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^MG[0-9a-fA-F]{32}$` |
| `default_inactive_timer` | `str` | Form, Optional | Default ISO8601 duration when conversation will be switched to `inactive` state. Minimum value for this timer is 1 minute. |
| `default_closed_timer` | `str` | Form, Optional | Default ISO8601 duration when conversation will be switched to `closed` state. Minimum value for this timer is 10 minutes. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Configuration`](../../doc/models/configuration.md).

## Example Usage

```python
default_chat_service_sid = 'ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

default_messaging_service_sid = 'MGaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

default_inactive_timer = 'PT1M'

default_closed_timer = 'PT10M'

result = conversations_v_1_configuration_api.update_configuration(
    default_chat_service_sid=default_chat_service_sid,
    default_messaging_service_sid=default_messaging_service_sid,
    default_inactive_timer=default_inactive_timer,
    default_closed_timer=default_closed_timer
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
  "default_chat_service_sid": "ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "default_messaging_service_sid": "MGaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "default_inactive_timer": "PT1M",
  "default_closed_timer": "PT10M",
  "url": "https://conversations.twilio.com/v1/Configuration",
  "links": {
    "service": "https://conversations.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Configuration",
    "webhooks": "https://conversations.twilio.com/v1/Configuration/Webhooks"
  }
}
```


# Fetch Service Configuration

Fetch the configuration of a conversation service

```python
def fetch_service_configuration(self,
                               chat_service_sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the Service configuration resource to fetch.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ServiceConfiguration`](../../doc/models/service-configuration.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

result = conversations_v_1_configuration_api.fetch_service_configuration(chat_service_sid)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "chat_service_sid": "ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "default_conversation_creator_role_sid": "RLaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "default_conversation_role_sid": "RLaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "default_chat_service_role_sid": "RLaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "reachability_enabled": false,
  "url": "https://conversations.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Configuration",
  "links": {
    "notifications": "https://conversations.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Configuration/Notifications",
    "webhooks": "https://conversations.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Configuration/Webhooks"
  }
}
```


# Update Service Configuration

Update configuration settings of a conversation service

```python
def update_service_configuration(self,
                                chat_service_sid,
                                default_conversation_creator_role_sid=None,
                                default_conversation_role_sid=None,
                                default_chat_service_role_sid=None,
                                reachability_enabled=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the Service configuration resource to update.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `default_conversation_creator_role_sid` | `str` | Form, Optional | The conversation-level role assigned to a conversation creator when they join a new conversation. See [Conversation Role](https://www.twilio.com/docs/conversations/api/role-resource) for more info about roles.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^RL[0-9a-fA-F]{32}$` |
| `default_conversation_role_sid` | `str` | Form, Optional | The conversation-level role assigned to users when they are added to a conversation. See [Conversation Role](https://www.twilio.com/docs/conversations/api/role-resource) for more info about roles.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^RL[0-9a-fA-F]{32}$` |
| `default_chat_service_role_sid` | `str` | Form, Optional | The service-level role assigned to users when they are added to the service. See [Conversation Role](https://www.twilio.com/docs/conversations/api/role-resource) for more info about roles.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^RL[0-9a-fA-F]{32}$` |
| `reachability_enabled` | `bool` | Form, Optional | Whether the [Reachability Indicator](https://www.twilio.com/docs/conversations/reachability) is enabled for this Conversations Service. The default is `false`. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ServiceConfiguration`](../../doc/models/service-configuration.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

default_conversation_creator_role_sid = 'RLaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

default_conversation_role_sid = 'RLaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

default_chat_service_role_sid = 'RLaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

reachability_enabled = False

result = conversations_v_1_configuration_api.update_service_configuration(
    chat_service_sid,
    default_conversation_creator_role_sid=default_conversation_creator_role_sid,
    default_conversation_role_sid=default_conversation_role_sid,
    default_chat_service_role_sid=default_chat_service_role_sid,
    reachability_enabled=reachability_enabled
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "chat_service_sid": "ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "default_conversation_creator_role_sid": "RLaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "default_conversation_role_sid": "RLaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "default_chat_service_role_sid": "RLaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "reachability_enabled": false,
  "url": "https://conversations.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Configuration",
  "links": {
    "notifications": "https://conversations.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Configuration/Notifications",
    "webhooks": "https://conversations.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Configuration/Webhooks"
  }
}
```

