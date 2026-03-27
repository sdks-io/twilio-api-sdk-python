# Notify V1 Service

```python
notify_v_1_service_api = client.notify_v_1_service
```

## Class Name

`NotifyV1ServiceApi`

## Methods

* [Create Service](../../doc/controllers/notify-v1-service.md#create-service)
* [List Service](../../doc/controllers/notify-v1-service.md#list-service)
* [Delete Service](../../doc/controllers/notify-v1-service.md#delete-service)
* [Fetch Service](../../doc/controllers/notify-v1-service.md#fetch-service)
* [Update Service](../../doc/controllers/notify-v1-service.md#update-service)


# Create Service

```python
def create_service(self,
                  friendly_name=None,
                  apn_credential_sid=None,
                  gcm_credential_sid=None,
                  messaging_service_sid=None,
                  facebook_messenger_page_id=None,
                  default_apn_notification_protocol_version=None,
                  default_gcm_notification_protocol_version=None,
                  fcm_credential_sid=None,
                  default_fcm_notification_protocol_version=None,
                  log_enabled=None,
                  alexa_skill_id=None,
                  default_alexa_notification_protocol_version=None,
                  delivery_callback_url=None,
                  delivery_callback_enabled=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `friendly_name` | `str` | Form, Optional | A descriptive string that you create to describe the resource. It can be up to 64 characters long. |
| `apn_credential_sid` | `str` | Form, Optional | The SID of the [Credential](https://www.twilio.com/docs/notify/api/credential-resource) to use for APN Bindings.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^CR[0-9a-fA-F]{32}$` |
| `gcm_credential_sid` | `str` | Form, Optional | The SID of the [Credential](https://www.twilio.com/docs/notify/api/credential-resource) to use for GCM Bindings.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^CR[0-9a-fA-F]{32}$` |
| `messaging_service_sid` | `str` | Form, Optional | The SID of the [Messaging Service](https://www.twilio.com/docs/sms/quickstart#messaging-services) to use for SMS Bindings. This parameter must be set in order to send SMS notifications.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^MG[0-9a-fA-F]{32}$` |
| `facebook_messenger_page_id` | `str` | Form, Optional | Deprecated. |
| `default_apn_notification_protocol_version` | `str` | Form, Optional | The protocol version to use for sending APNS notifications. Can be overridden on a Binding by Binding basis when creating a [Binding](https://www.twilio.com/docs/notify/api/binding-resource) resource. |
| `default_gcm_notification_protocol_version` | `str` | Form, Optional | The protocol version to use for sending GCM notifications. Can be overridden on a Binding by Binding basis when creating a [Binding](https://www.twilio.com/docs/notify/api/binding-resource) resource. |
| `fcm_credential_sid` | `str` | Form, Optional | The SID of the [Credential](https://www.twilio.com/docs/notify/api/credential-resource) to use for FCM Bindings.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^CR[0-9a-fA-F]{32}$` |
| `default_fcm_notification_protocol_version` | `str` | Form, Optional | The protocol version to use for sending FCM notifications. Can be overridden on a Binding by Binding basis when creating a [Binding](https://www.twilio.com/docs/notify/api/binding-resource) resource. |
| `log_enabled` | `bool` | Form, Optional | Whether to log notifications. Can be: `true` or `false` and the default is `true`. |
| `alexa_skill_id` | `str` | Form, Optional | Deprecated. |
| `default_alexa_notification_protocol_version` | `str` | Form, Optional | Deprecated. |
| `delivery_callback_url` | `str` | Form, Optional | URL to send delivery status callback. |
| `delivery_callback_enabled` | `bool` | Form, Optional | Callback configuration that enables delivery callbacks, default false |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Service1`](../../doc/models/service-1.md).

## Example Usage

```python
friendly_name = 'friendly_name'

apn_credential_sid = 'CRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

messaging_service_sid = 'MGaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

facebook_messenger_page_id = '4'

default_apn_notification_protocol_version = '3'

default_gcm_notification_protocol_version = '3'

default_fcm_notification_protocol_version = '3'

log_enabled = True

delivery_callback_url = 'Hello'

delivery_callback_enabled = True

result = notify_v_1_service_api.create_service(
    friendly_name=friendly_name,
    apn_credential_sid=apn_credential_sid,
    messaging_service_sid=messaging_service_sid,
    facebook_messenger_page_id=facebook_messenger_page_id,
    default_apn_notification_protocol_version=default_apn_notification_protocol_version,
    default_gcm_notification_protocol_version=default_gcm_notification_protocol_version,
    default_fcm_notification_protocol_version=default_fcm_notification_protocol_version,
    log_enabled=log_enabled,
    delivery_callback_url=delivery_callback_url,
    delivery_callback_enabled=delivery_callback_enabled
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "sid": "ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "friendly_name": "733c7f0f-6541-42ec-84ce-e2ae1cac588c",
  "date_created": "2016-03-09T20:22:31Z",
  "date_updated": "2016-03-09T20:22:31Z",
  "apn_credential_sid": null,
  "gcm_credential_sid": null,
  "fcm_credential_sid": null,
  "messaging_service_sid": "MGaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "facebook_messenger_page_id": "4",
  "alexa_skill_id": null,
  "default_apn_notification_protocol_version": "3",
  "default_gcm_notification_protocol_version": "3",
  "default_fcm_notification_protocol_version": "3",
  "default_alexa_notification_protocol_version": "3",
  "log_enabled": true,
  "delivery_callback_url": "Hello",
  "delivery_callback_enabled": true,
  "url": "https://notify.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "links": {
    "bindings": "https://notify.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Bindings",
    "notifications": "https://notify.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Notifications",
    "segments": "https://notify.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Segments",
    "users": "https://notify.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Users"
  }
}
```


# List Service

```python
def list_service(self,
                friendly_name=None,
                page_size=None,
                page=None,
                page_token=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `friendly_name` | `str` | Query, Optional | The string that identifies the Service resources to read. |
| `page_size` | `int` | Query, Optional | How many resources to return in each list page. The default is 50, and the maximum is 1000.<br><br>**Constraints**: `>= 1`, `<= 1000` |
| `page` | `int` | Query, Optional | The page index. This value is simply for client state.<br><br>**Constraints**: `>= 0` |
| `page_token` | `str` | Query, Optional | The page token. This is provided by the API. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ListServiceResponse`](../../doc/models/list-service-response.md).

## Example Usage

```python
result = notify_v_1_service_api.list_service()

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
    "first_page_url": "https://notify.twilio.com/v1/Services?PageSize=50&Page=0",
    "previous_page_url": null,
    "url": "https://notify.twilio.com/v1/Services?PageSize=50&Page=0",
    "next_page_url": null,
    "key": "services"
  },
  "services": [
    {
      "sid": "ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "friendly_name": "733c7f0f-6541-42ec-84ce-e2ae1cac588c",
      "date_created": "2016-03-09T20:22:31Z",
      "date_updated": "2016-03-09T20:22:31Z",
      "apn_credential_sid": null,
      "gcm_credential_sid": null,
      "fcm_credential_sid": null,
      "messaging_service_sid": "MGaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "facebook_messenger_page_id": "4",
      "alexa_skill_id": null,
      "default_apn_notification_protocol_version": "3",
      "default_gcm_notification_protocol_version": "3",
      "default_fcm_notification_protocol_version": "3",
      "default_alexa_notification_protocol_version": "3",
      "log_enabled": true,
      "delivery_callback_url": "Hello",
      "delivery_callback_enabled": true,
      "url": "https://notify.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "links": {
        "bindings": "https://notify.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Bindings",
        "notifications": "https://notify.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Notifications",
        "segments": "https://notify.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Segments",
        "users": "https://notify.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Users"
      }
    }
  ]
}
```


# Delete Service

```python
def delete_service(self,
                  sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sid` | `str` | Template, Required | The Twilio-provided string that uniquely identifies the Service resource to delete.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```python
sid = 'Sid8'

result = notify_v_1_service_api.delete_service(sid)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Fetch Service

```python
def fetch_service(self,
                 sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sid` | `str` | Template, Required | The Twilio-provided string that uniquely identifies the Service resource to fetch.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Service1`](../../doc/models/service-1.md).

## Example Usage

```python
sid = 'Sid8'

result = notify_v_1_service_api.fetch_service(sid)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "sid": "ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "friendly_name": "733c7f0f-6541-42ec-84ce-e2ae1cac588c",
  "date_created": "2016-03-09T20:22:31Z",
  "date_updated": "2016-03-09T20:22:31Z",
  "apn_credential_sid": null,
  "gcm_credential_sid": null,
  "fcm_credential_sid": null,
  "messaging_service_sid": "MGaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "facebook_messenger_page_id": "4",
  "alexa_skill_id": null,
  "default_apn_notification_protocol_version": "3",
  "default_gcm_notification_protocol_version": "3",
  "default_fcm_notification_protocol_version": "3",
  "default_alexa_notification_protocol_version": "3",
  "log_enabled": true,
  "delivery_callback_url": "Hello",
  "delivery_callback_enabled": true,
  "url": "https://notify.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "links": {
    "bindings": "https://notify.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Bindings",
    "notifications": "https://notify.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Notifications",
    "segments": "https://notify.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Segments",
    "users": "https://notify.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Users"
  }
}
```


# Update Service

```python
def update_service(self,
                  sid,
                  friendly_name=None,
                  apn_credential_sid=None,
                  gcm_credential_sid=None,
                  messaging_service_sid=None,
                  facebook_messenger_page_id=None,
                  default_apn_notification_protocol_version=None,
                  default_gcm_notification_protocol_version=None,
                  fcm_credential_sid=None,
                  default_fcm_notification_protocol_version=None,
                  log_enabled=None,
                  alexa_skill_id=None,
                  default_alexa_notification_protocol_version=None,
                  delivery_callback_url=None,
                  delivery_callback_enabled=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sid` | `str` | Template, Required | The Twilio-provided string that uniquely identifies the Service resource to update.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `friendly_name` | `str` | Form, Optional | A descriptive string that you create to describe the resource. It can be up to 64 characters long. |
| `apn_credential_sid` | `str` | Form, Optional | The SID of the [Credential](https://www.twilio.com/docs/notify/api/credential-resource) to use for APN Bindings.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^CR[0-9a-fA-F]{32}$` |
| `gcm_credential_sid` | `str` | Form, Optional | The SID of the [Credential](https://www.twilio.com/docs/notify/api/credential-resource) to use for GCM Bindings.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^CR[0-9a-fA-F]{32}$` |
| `messaging_service_sid` | `str` | Form, Optional | The SID of the [Messaging Service](https://www.twilio.com/docs/sms/quickstart#messaging-services) to use for SMS Bindings. This parameter must be set in order to send SMS notifications.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^MG[0-9a-fA-F]{32}$` |
| `facebook_messenger_page_id` | `str` | Form, Optional | Deprecated. |
| `default_apn_notification_protocol_version` | `str` | Form, Optional | The protocol version to use for sending APNS notifications. Can be overridden on a Binding by Binding basis when creating a [Binding](https://www.twilio.com/docs/notify/api/binding-resource) resource. |
| `default_gcm_notification_protocol_version` | `str` | Form, Optional | The protocol version to use for sending GCM notifications. Can be overridden on a Binding by Binding basis when creating a [Binding](https://www.twilio.com/docs/notify/api/binding-resource) resource. |
| `fcm_credential_sid` | `str` | Form, Optional | The SID of the [Credential](https://www.twilio.com/docs/notify/api/credential-resource) to use for FCM Bindings.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^CR[0-9a-fA-F]{32}$` |
| `default_fcm_notification_protocol_version` | `str` | Form, Optional | The protocol version to use for sending FCM notifications. Can be overridden on a Binding by Binding basis when creating a [Binding](https://www.twilio.com/docs/notify/api/binding-resource) resource. |
| `log_enabled` | `bool` | Form, Optional | Whether to log notifications. Can be: `true` or `false` and the default is `true`. |
| `alexa_skill_id` | `str` | Form, Optional | Deprecated. |
| `default_alexa_notification_protocol_version` | `str` | Form, Optional | Deprecated. |
| `delivery_callback_url` | `str` | Form, Optional | URL to send delivery status callback. |
| `delivery_callback_enabled` | `bool` | Form, Optional | Callback configuration that enables delivery callbacks, default false |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Service1`](../../doc/models/service-1.md).

## Example Usage

```python
sid = 'Sid8'

friendly_name = 'friendly_name'

apn_credential_sid = 'CRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

messaging_service_sid = 'MGaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

facebook_messenger_page_id = '4'

default_apn_notification_protocol_version = '3'

default_gcm_notification_protocol_version = '3'

default_fcm_notification_protocol_version = '3'

log_enabled = True

delivery_callback_url = 'Hello'

delivery_callback_enabled = True

result = notify_v_1_service_api.update_service(
    sid,
    friendly_name=friendly_name,
    apn_credential_sid=apn_credential_sid,
    messaging_service_sid=messaging_service_sid,
    facebook_messenger_page_id=facebook_messenger_page_id,
    default_apn_notification_protocol_version=default_apn_notification_protocol_version,
    default_gcm_notification_protocol_version=default_gcm_notification_protocol_version,
    default_fcm_notification_protocol_version=default_fcm_notification_protocol_version,
    log_enabled=log_enabled,
    delivery_callback_url=delivery_callback_url,
    delivery_callback_enabled=delivery_callback_enabled
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "sid": "ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "friendly_name": "733c7f0f-6541-42ec-84ce-e2ae1cac588c",
  "date_created": "2016-03-09T20:22:31Z",
  "date_updated": "2016-03-09T20:22:31Z",
  "apn_credential_sid": null,
  "gcm_credential_sid": null,
  "fcm_credential_sid": null,
  "default_apn_notification_protocol_version": "3",
  "default_gcm_notification_protocol_version": "3",
  "default_fcm_notification_protocol_version": "3",
  "default_alexa_notification_protocol_version": "3",
  "messaging_service_sid": "MGaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "alexa_skill_id": null,
  "facebook_messenger_page_id": "4",
  "log_enabled": true,
  "delivery_callback_url": "Hello",
  "delivery_callback_enabled": true,
  "url": "https://notify.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "links": {
    "bindings": "https://notify.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Bindings",
    "notifications": "https://notify.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Notifications",
    "segments": "https://notify.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Segments",
    "users": "https://notify.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Users"
  }
}
```

