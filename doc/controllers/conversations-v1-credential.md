# Conversations V1 Credential

```python
conversations_v_1_credential_api = client.conversations_v_1_credential
```

## Class Name

`ConversationsV1CredentialApi`

## Methods

* [Create Credential](../../doc/controllers/conversations-v1-credential.md#create-credential)
* [List Credential](../../doc/controllers/conversations-v1-credential.md#list-credential)
* [Update Credential](../../doc/controllers/conversations-v1-credential.md#update-credential)
* [Delete Credential](../../doc/controllers/conversations-v1-credential.md#delete-credential)
* [Fetch Credential](../../doc/controllers/conversations-v1-credential.md#fetch-credential)


# Create Credential

Add a new push notification credential to your account

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
| `mtype` | [`CredentialPushType`](../../doc/models/credential-push-type.md) | Form, Required | The type of push-notification service the credential is for. Can be: `fcm`, `gcm`, or `apn`. |
| `friendly_name` | `str` | Form, Optional | A descriptive string that you create to describe the new resource. It can be up to 64 characters long. |
| `certificate` | `str` | Form, Optional | [APN only] The URL encoded representation of the certificate. For example,<br>`-----BEGIN CERTIFICATE----- MIIFnTCCBIWgAwIBAgIIAjy9H849+E8wDQYJKoZIhvcNAQEF.....A== -----END CERTIFICATE-----`. |
| `private_key` | `str` | Form, Optional | [APN only] The URL encoded representation of the private key. For example,<br>`-----BEGIN RSA PRIVATE KEY----- MIIEpQIBAAKCAQEAuyf/lNrH9ck8DmNyo3fG... -----END RSA PRIVATE KEY-----`. |
| `sandbox` | `bool` | Form, Optional | [APN only] Whether to send the credential to sandbox APNs. Can be `true` to send to sandbox APNs or `false` to send to production. |
| `api_key` | `str` | Form, Optional | [GCM only] The API key for the project that was obtained from the Google Developer console for your GCM Service application credential. |
| `secret` | `str` | Form, Optional | [FCM only] The **Server key** of your project from the Firebase console, found under Settings / Cloud messaging. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Credential`](../../doc/models/credential.md).

## Example Usage

```python
mtype = CredentialPushType.APN

result = conversations_v_1_credential_api.create_credential(mtype)

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
  "url": "https://conversations.twilio.com/v1/Credentials/CRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
}
```


# List Credential

Retrieve a list of all push notification credentials on your account

```python
def list_credential(self,
                   page_size=None,
                   page=None,
                   page_token=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `page_size` | `int` | Query, Optional | How many resources to return in each list page. The default is 50, and the maximum is 100.<br><br>**Constraints**: `>= 1`, `<= 100` |
| `page` | `int` | Query, Optional | The page index. This value is simply for client state.<br><br>**Constraints**: `>= 0` |
| `page_token` | `str` | Query, Optional | The page token. This is provided by the API. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ListCredentialResponse`](../../doc/models/list-credential-response.md).

## Example Usage

```python
result = conversations_v_1_credential_api.list_credential()

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
      "url": "https://conversations.twilio.com/v1/Credentials/CRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
    }
  ],
  "meta": {
    "page": 0,
    "page_size": 50,
    "first_page_url": "https://conversations.twilio.com/v1/Credentials?PageSize=50&Page=0",
    "previous_page_url": null,
    "url": "https://conversations.twilio.com/v1/Credentials?PageSize=50&Page=0",
    "next_page_url": null,
    "key": "credentials"
  }
}
```


# Update Credential

Update an existing push notification credential on your account

```python
def update_credential(self,
                     sid,
                     mtype=None,
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
| `sid` | `str` | Template, Required | A 34 character string that uniquely identifies this resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^CR[0-9a-fA-F]{32}$` |
| `mtype` | [`CredentialPushType`](../../doc/models/credential-push-type.md) | Form, Optional | The type of push-notification service the credential is for. Can be: `fcm`, `gcm`, or `apn`. |
| `friendly_name` | `str` | Form, Optional | A descriptive string that you create to describe the new resource. It can be up to 64 characters long. |
| `certificate` | `str` | Form, Optional | [APN only] The URL encoded representation of the certificate. For example,<br>`-----BEGIN CERTIFICATE----- MIIFnTCCBIWgAwIBAgIIAjy9H849+E8wDQYJKoZIhvcNAQEF.....A== -----END CERTIFICATE-----`. |
| `private_key` | `str` | Form, Optional | [APN only] The URL encoded representation of the private key. For example,<br>`-----BEGIN RSA PRIVATE KEY----- MIIEpQIBAAKCAQEAuyf/lNrH9ck8DmNyo3fG... -----END RSA PRIVATE KEY-----`. |
| `sandbox` | `bool` | Form, Optional | [APN only] Whether to send the credential to sandbox APNs. Can be `true` to send to sandbox APNs or `false` to send to production. |
| `api_key` | `str` | Form, Optional | [GCM only] The API key for the project that was obtained from the Google Developer console for your GCM Service application credential. |
| `secret` | `str` | Form, Optional | [FCM only] The **Server key** of your project from the Firebase console, found under Settings / Cloud messaging. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Credential`](../../doc/models/credential.md).

## Example Usage

```python
sid = 'Sid8'

friendly_name = 'Test slow create'

result = conversations_v_1_credential_api.update_credential(
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
  "url": "https://conversations.twilio.com/v1/Credentials/CRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
}
```


# Delete Credential

Remove a push notification credential from your account

```python
def delete_credential(self,
                     sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sid` | `str` | Template, Required | A 34 character string that uniquely identifies this resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^CR[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```python
sid = 'Sid8'

result = conversations_v_1_credential_api.delete_credential(sid)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Fetch Credential

Fetch a push notification credential from your account

```python
def fetch_credential(self,
                    sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sid` | `str` | Template, Required | A 34 character string that uniquely identifies this resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^CR[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Credential`](../../doc/models/credential.md).

## Example Usage

```python
sid = 'Sid8'

result = conversations_v_1_credential_api.fetch_credential(sid)

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
  "url": "https://conversations.twilio.com/v1/Credentials/CRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
}
```

