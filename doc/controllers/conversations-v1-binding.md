# Conversations V1 Binding

```python
conversations_v_1_binding_api = client.conversations_v_1_binding
```

## Class Name

`ConversationsV1BindingApi`

## Methods

* [Delete Service Binding](../../doc/controllers/conversations-v1-binding.md#delete-service-binding)
* [Fetch Service Binding](../../doc/controllers/conversations-v1-binding.md#fetch-service-binding)
* [List Service Binding](../../doc/controllers/conversations-v1-binding.md#list-service-binding)


# Delete Service Binding

Remove a push notification binding from the conversation service

```python
def delete_service_binding(self,
                          chat_service_sid,
                          sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) to delete the Binding resource from.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `sid` | `str` | Template, Required | The SID of the Binding resource to delete.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^BS[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

sid = 'Sid8'

result = conversations_v_1_binding_api.delete_service_binding(
    chat_service_sid,
    sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Fetch Service Binding

Fetch a push notification binding from the conversation service

```python
def fetch_service_binding(self,
                         chat_service_sid,
                         sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Binding resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `sid` | `str` | Template, Required | A 34 character string that uniquely identifies this resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^BS[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ServiceBinding`](../../doc/models/service-binding.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

sid = 'Sid8'

result = conversations_v_1_binding_api.fetch_service_binding(
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
  "sid": "BSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "chat_service_sid": "ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "date_created": "2016-10-21T11:37:03Z",
  "date_updated": "2016-10-21T11:37:03Z",
  "endpoint": "TestUser-endpoint",
  "identity": "TestUser",
  "binding_type": "gcm",
  "credential_sid": "CRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "message_types": [
    "removed_from_conversation",
    "new_message",
    "added_to_conversation"
  ],
  "url": "https://conversations.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Bindings/BSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
}
```


# List Service Binding

Retrieve a list of all push notification bindings in the conversation service

```python
def list_service_binding(self,
                        chat_service_sid,
                        binding_type=None,
                        identity=None,
                        page_size=None,
                        page=None,
                        page_token=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chat_service_sid` | `str` | Template, Required | The SID of the [Conversation Service](https://www.twilio.com/docs/conversations/api/service-resource) the Binding resource is associated with.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `binding_type` | [`List[ServiceBindingBindingType]`](../../doc/models/service-binding-binding-type.md) | Query, Optional | The push technology used by the Binding resources to read.  Can be: `apn`, `gcm`, `fcm`, or `twilsock`.  See [push notification configuration](https://www.twilio.com/docs/chat/push-notification-configuration) for more info. |
| `identity` | `List[str]` | Query, Optional | The identity of a [Conversation User](https://www.twilio.com/docs/conversations/api/user-resource) this binding belongs to. See [access tokens](https://www.twilio.com/docs/conversations/create-tokens) for more details. |
| `page_size` | `int` | Query, Optional | How many resources to return in each list page. The default is 50, and the maximum is 100.<br><br>**Constraints**: `>= 1`, `<= 100` |
| `page` | `int` | Query, Optional | The page index. This value is simply for client state.<br><br>**Constraints**: `>= 0` |
| `page_token` | `str` | Query, Optional | The page token. This is provided by the API. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ListServiceBindingResponse`](../../doc/models/list-service-binding-response.md).

## Example Usage

```python
chat_service_sid = 'ChatServiceSid4'

result = conversations_v_1_binding_api.list_service_binding(chat_service_sid)

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
    "first_page_url": "https://conversations.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Bindings?PageSize=50&Page=0",
    "previous_page_url": null,
    "url": "https://conversations.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Bindings?PageSize=50&Page=0",
    "next_page_url": null,
    "key": "bindings"
  },
  "bindings": [
    {
      "sid": "BSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "chat_service_sid": "ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "date_created": "2016-10-21T11:37:03Z",
      "date_updated": "2016-10-21T11:37:03Z",
      "endpoint": "TestUser-endpoint",
      "identity": "TestUser",
      "binding_type": "gcm",
      "credential_sid": "CRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "message_types": [
        "removed_from_conversation",
        "new_message",
        "added_to_conversation"
      ],
      "url": "https://conversations.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Bindings/BSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
    }
  ]
}
```

