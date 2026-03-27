# Notify V1 Binding

```python
notify_v_1_binding_api = client.notify_v_1_binding
```

## Class Name

`NotifyV1BindingApi`

## Methods

* [Fetch Binding](../../doc/controllers/notify-v1-binding.md#fetch-binding)
* [Delete Binding](../../doc/controllers/notify-v1-binding.md#delete-binding)
* [Create Binding](../../doc/controllers/notify-v1-binding.md#create-binding)
* [List Binding](../../doc/controllers/notify-v1-binding.md#list-binding)


# Fetch Binding

```python
def fetch_binding(self,
                 service_sid,
                 sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `service_sid` | `str` | Template, Required | The SID of the [Service](https://www.twilio.com/docs/notify/api/service-resource) to fetch the resource from.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `sid` | `str` | Template, Required | The Twilio-provided string that uniquely identifies the Binding resource to fetch.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^BS[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Binding`](../../doc/models/binding.md).

## Example Usage

```python
service_sid = 'ServiceSid8'

sid = 'Sid8'

result = notify_v_1_binding_api.fetch_binding(
    service_sid,
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
  "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "address": "a7c658f4111ec4ff5a1a647f9d0edd819025b9f20522d2fae897049f32873e73",
  "binding_type": "apn",
  "credential_sid": null,
  "date_created": "2015-07-30T20:00:00Z",
  "date_updated": "2015-07-30T20:00:00Z",
  "endpoint": "26607274",
  "identity": "24987039",
  "notification_protocol_version": "3",
  "service_sid": "ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "sid": "BSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "tags": [
    "26607274"
  ],
  "links": {
    "user": "https://notify.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Users/24987039"
  },
  "url": "https://notify.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Bindings/BSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
}
```


# Delete Binding

```python
def delete_binding(self,
                  service_sid,
                  sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `service_sid` | `str` | Template, Required | The SID of the [Service](https://www.twilio.com/docs/notify/api/service-resource) to delete the resource from.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `sid` | `str` | Template, Required | The Twilio-provided string that uniquely identifies the Binding resource to delete.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^BS[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```python
service_sid = 'ServiceSid8'

sid = 'Sid8'

result = notify_v_1_binding_api.delete_binding(
    service_sid,
    sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Create Binding

```python
def create_binding(self,
                  service_sid,
                  identity,
                  binding_type,
                  address,
                  tag=None,
                  notification_protocol_version=None,
                  credential_sid=None,
                  endpoint=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `service_sid` | `str` | Template, Required | The SID of the [Service](https://www.twilio.com/docs/notify/api/service-resource) to create the resource under.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `identity` | `str` | Form, Required | The `identity` value that uniquely identifies the new resource's [User](https://www.twilio.com/docs/chat/rest/user-resource) within the [Service](https://www.twilio.com/docs/notify/api/service-resource). Up to 20 Bindings can be created for the same Identity in a given Service. |
| `binding_type` | [`BindingBindingType`](../../doc/models/binding-binding-type.md) | Form, Required | The transport technology to use for the Binding. Can be: `apn`, `fcm`, `gcm`, `sms`, or `facebook-messenger`. |
| `address` | `str` | Form, Required | The channel-specific address. For APNS, the device token. For FCM and GCM, the registration token. For SMS, a phone number in E.164 format. For Facebook Messenger, the Messenger ID of the user or a phone number in E.164 format. |
| `tag` | `List[str]` | Form, Optional | A tag that can be used to select the Bindings to notify. Repeat this parameter to specify more than one tag, up to a total of 20 tags. |
| `notification_protocol_version` | `str` | Form, Optional | The protocol version to use to send the notification. This defaults to the value of `default_xxxx_notification_protocol_version` for the protocol in the [Service](https://www.twilio.com/docs/notify/api/service-resource). The current version is `"3"` for `apn`, `fcm`, and `gcm` type Bindings. The parameter is not applicable to `sms` and `facebook-messenger` type Bindings as the data format is fixed. |
| `credential_sid` | `str` | Form, Optional | The SID of the [Credential](https://www.twilio.com/docs/notify/api/credential-resource) resource to be used to send notifications to this Binding. If present, this overrides the Credential specified in the Service resource. Applies to only `apn`, `fcm`, and `gcm` type Bindings.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^CR[0-9a-fA-F]{32}$` |
| `endpoint` | `str` | Form, Optional | Deprecated. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Binding`](../../doc/models/binding.md).

## Example Usage

```python
service_sid = 'ServiceSid8'

identity = '24987039'

binding_type = BindingBindingType.APN

address = 'address'

tag = [
    'tag'
]

notification_protocol_version = 'notification_protocol_version'

credential_sid = 'CRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

endpoint = 'endpoint'

result = notify_v_1_binding_api.create_binding(
    service_sid,
    identity,
    binding_type,
    address,
    tag=tag,
    notification_protocol_version=notification_protocol_version,
    credential_sid=credential_sid,
    endpoint=endpoint
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
  "address": "a7c658f4111ec4ff5a1a647f9d0edd819025b9f20522d2fae897049f32873e73",
  "binding_type": "apn",
  "credential_sid": null,
  "date_created": "2015-07-30T20:00:00Z",
  "date_updated": "2015-07-30T20:00:00Z",
  "endpoint": "26607274",
  "identity": "24987039",
  "notification_protocol_version": "3",
  "service_sid": "ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "sid": "BSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "tags": [
    "26607274"
  ],
  "links": {
    "user": "https://notify.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Users/24987039"
  },
  "url": "https://notify.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Bindings/BSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
}
```


# List Binding

```python
def list_binding(self,
                service_sid,
                start_date=None,
                end_date=None,
                identity=None,
                tag=None,
                page_size=None,
                page=None,
                page_token=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `service_sid` | `str` | Template, Required | The SID of the [Service](https://www.twilio.com/docs/notify/api/service-resource) to read the resource from.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `start_date` | `date` | Query, Optional | Only include usage that has occurred on or after this date. Specify the date in GMT and format as `YYYY-MM-DD`. |
| `end_date` | `date` | Query, Optional | Only include usage that occurred on or before this date. Specify the date in GMT and format as `YYYY-MM-DD`. |
| `identity` | `List[str]` | Query, Optional | The [User](https://www.twilio.com/docs/chat/rest/user-resource)'s `identity` value of the resources to read. |
| `tag` | `List[str]` | Query, Optional | Only list Bindings that have all of the specified Tags. The following implicit tags are available: `all`, `apn`, `fcm`, `gcm`, `sms`, `facebook-messenger`. Up to 5 tags are allowed. |
| `page_size` | `int` | Query, Optional | How many resources to return in each list page. The default is 50, and the maximum is 1000.<br><br>**Constraints**: `>= 1`, `<= 1000` |
| `page` | `int` | Query, Optional | The page index. This value is simply for client state.<br><br>**Constraints**: `>= 0` |
| `page_token` | `str` | Query, Optional | The page token. This is provided by the API. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ListBindingResponse`](../../doc/models/list-binding-response.md).

## Example Usage

```python
service_sid = 'ServiceSid8'

identity = [
    'identity'
]

tag = [
    'tag'
]

result = notify_v_1_binding_api.list_binding(
    service_sid,
    identity=identity,
    tag=tag
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "bindings": [],
  "meta": {
    "first_page_url": "https://notify.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Bindings?Tag=tag&Identity=identity&PageSize=50&Page=0",
    "key": "bindings",
    "next_page_url": null,
    "page": 0,
    "page_size": 50,
    "previous_page_url": null,
    "url": "https://notify.twilio.com/v1/Services/ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Bindings?Tag=tag&Identity=identity&PageSize=50&Page=0"
  }
}
```

