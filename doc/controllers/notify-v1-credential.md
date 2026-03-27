# Notify V1 Credential

```python
notify_v_1_credential_api = client.notify_v_1_credential
```

## Class Name

`NotifyV1CredentialApi`

## Methods

* [List Credential](../../doc/controllers/notify-v1-credential.md#list-credential)
* [Create Credential](../../doc/controllers/notify-v1-credential.md#create-credential)
* [Fetch Credential](../../doc/controllers/notify-v1-credential.md#fetch-credential)
* [Update Credential](../../doc/controllers/notify-v1-credential.md#update-credential)
* [Delete Credential](../../doc/controllers/notify-v1-credential.md#delete-credential)


# List Credential

```python
def list_credential(self,
                   page_size=None,
                   page=None,
                   page_token=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `page_size` | `int` | Query, Optional | How many resources to return in each list page. The default is 50, and the maximum is 1000.<br><br>**Constraints**: `>= 1`, `<= 1000` |
| `page` | `int` | Query, Optional | The page index. This value is simply for client state.<br><br>**Constraints**: `>= 0` |
| `page_token` | `str` | Query, Optional | The page token. This is provided by the API. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ListCredentialResponse`](../../doc/models/list-credential-response.md).

## Example Usage

```python
result = notify_v_1_credential_api.list_credential()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "credentials": [
    {
      "sid": "CRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "friendly_name": "Test slow create",
      "type": "apn",
      "sandbox": "False",
      "date_created": "2015-10-07T17:50:01Z",
      "date_updated": "2015-10-07T17:50:01Z",
      "url": "https://notify.twilio.com/v1/Credentials/CRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
    }
  ],
  "meta": {
    "page": 0,
    "page_size": 50,
    "first_page_url": "https://notify.twilio.com/v1/Credentials?PageSize=50&Page=0",
    "previous_page_url": null,
    "url": "https://notify.twilio.com/v1/Credentials?PageSize=50&Page=0",
    "next_page_url": null,
    "key": "credentials"
  }
}
```


# Create Credential

```python
def create_credential(self,
                     mtype,
                     friendly_name=None,
                     certificate=None,
                     private_key=None,
                     sandbox=None,
                     api_key=None,
                     secret=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `mtype` | [`CredentialPushType`](../../doc/models/credential-push-type.md) | Form, Required | The Credential type. Can be: `gcm`, `fcm`, or `apn`. |
| `friendly_name` | `str` | Form, Optional | A descriptive string that you create to describe the resource. It can be up to 64 characters long. |
| `certificate` | `str` | Form, Optional | [APN only] The URL-encoded representation of the certificate. Strip everything outside of the headers, e.g. `-----BEGIN CERTIFICATE-----MIIFnTCCBIWgAwIBAgIIAjy9H849+E8wDQYJKoZIhvcNAQEFBQAwgZYxCzAJBgNV.....A==-----END CERTIFICATE-----` |
| `private_key` | `str` | Form, Optional | [APN only] The URL-encoded representation of the private key. Strip everything outside of the headers, e.g. `-----BEGIN RSA PRIVATE KEY-----MIIEpQIBAAKCAQEAuyf/lNrH9ck8DmNyo3fGgvCI1l9s+cmBY3WIz+cUDqmxiieR\n.-----END RSA PRIVATE KEY-----` |
| `sandbox` | `bool` | Form, Optional | [APN only] Whether to send the credential to sandbox APNs. Can be `true` to send to sandbox APNs or `false` to send to production. |
| `api_key` | `str` | Form, Optional | [GCM only] The `Server key` of your project from Firebase console under Settings / Cloud messaging. |
| `secret` | `str` | Form, Optional | [FCM only] The `Server key` of your project from Firebase console under Settings / Cloud messaging. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Credential1`](../../doc/models/credential-1.md).

## Example Usage

```python
mtype = CredentialPushType.APN

result = notify_v_1_credential_api.create_credential(mtype)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "sid": "CRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "friendly_name": "Test slow create",
  "type": "apn",
  "sandbox": "False",
  "date_created": "2015-10-07T17:50:01Z",
  "date_updated": "2015-10-07T17:50:01Z",
  "url": "https://notify.twilio.com/v1/Credentials/CRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
}
```


# Fetch Credential

```python
def fetch_credential(self,
                    sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sid` | `str` | Template, Required | The Twilio-provided string that uniquely identifies the Credential resource to fetch.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^CR[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Credential1`](../../doc/models/credential-1.md).

## Example Usage

```python
sid = 'Sid8'

result = notify_v_1_credential_api.fetch_credential(sid)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "sid": "CRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "friendly_name": "Test slow create",
  "type": "apn",
  "sandbox": "False",
  "date_created": "2015-10-07T17:50:01Z",
  "date_updated": "2015-10-07T17:50:01Z",
  "url": "https://notify.twilio.com/v1/Credentials/CRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
}
```


# Update Credential

```python
def update_credential(self,
                     sid,
                     friendly_name=None,
                     certificate=None,
                     private_key=None,
                     sandbox=None,
                     api_key=None,
                     secret=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sid` | `str` | Template, Required | The Twilio-provided string that uniquely identifies the Credential resource to update.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^CR[0-9a-fA-F]{32}$` |
| `friendly_name` | `str` | Form, Optional | A descriptive string that you create to describe the resource. It can be up to 64 characters long. |
| `certificate` | `str` | Form, Optional | [APN only] The URL-encoded representation of the certificate. Strip everything outside of the headers, e.g. `-----BEGIN CERTIFICATE-----MIIFnTCCBIWgAwIBAgIIAjy9H849+E8wDQYJKoZIhvcNAQEFBQAwgZYxCzAJBgNV.....A==-----END CERTIFICATE-----` |
| `private_key` | `str` | Form, Optional | [APN only] The URL-encoded representation of the private key. Strip everything outside of the headers, e.g. `-----BEGIN RSA PRIVATE KEY-----MIIEpQIBAAKCAQEAuyf/lNrH9ck8DmNyo3fGgvCI1l9s+cmBY3WIz+cUDqmxiieR\n.-----END RSA PRIVATE KEY-----` |
| `sandbox` | `bool` | Form, Optional | [APN only] Whether to send the credential to sandbox APNs. Can be `true` to send to sandbox APNs or `false` to send to production. |
| `api_key` | `str` | Form, Optional | [GCM only] The `Server key` of your project from Firebase console under Settings / Cloud messaging. |
| `secret` | `str` | Form, Optional | [FCM only] The `Server key` of your project from Firebase console under Settings / Cloud messaging. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Credential1`](../../doc/models/credential-1.md).

## Example Usage

```python
sid = 'Sid8'

friendly_name = 'Test slow create'

result = notify_v_1_credential_api.update_credential(
    sid,
    friendly_name=friendly_name
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "sid": "CRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "friendly_name": "Test slow create",
  "type": "apn",
  "sandbox": "False",
  "date_created": "2015-10-07T17:50:01Z",
  "date_updated": "2015-10-07T17:50:01Z",
  "url": "https://notify.twilio.com/v1/Credentials/CRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
}
```


# Delete Credential

```python
def delete_credential(self,
                     sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sid` | `str` | Template, Required | The Twilio-provided string that uniquely identifies the Credential resource to delete.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^CR[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```python
sid = 'Sid8'

result = notify_v_1_credential_api.delete_credential(sid)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

