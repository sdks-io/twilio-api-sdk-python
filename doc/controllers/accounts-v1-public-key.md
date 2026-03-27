# Accounts V1 Public Key

```python
accounts_v_1_public_key_api = client.accounts_v_1_public_key
```

## Class Name

`AccountsV1PublicKeyApi`

## Methods

* [List Credential Public Key](../../doc/controllers/accounts-v1-public-key.md#list-credential-public-key)
* [Create Credential Public Key](../../doc/controllers/accounts-v1-public-key.md#create-credential-public-key)
* [Fetch Credential Public Key](../../doc/controllers/accounts-v1-public-key.md#fetch-credential-public-key)
* [Update Credential Public Key](../../doc/controllers/accounts-v1-public-key.md#update-credential-public-key)
* [Delete Credential Public Key](../../doc/controllers/accounts-v1-public-key.md#delete-credential-public-key)


# List Credential Public Key

Retrieves a collection of Public Key Credentials belonging to the account used to make the request

```python
def list_credential_public_key(self,
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

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ListCredentialPublicKeyResponse`](../../doc/models/list-credential-public-key-response.md).

## Example Usage

```python
result = accounts_v_1_public_key_api.list_credential_public_key()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "credentials": [],
  "meta": {
    "first_page_url": "https://accounts.twilio.com/v1/Credentials/PublicKeys?PageSize=50&Page=0",
    "key": "credentials",
    "next_page_url": null,
    "page": 0,
    "page_size": 50,
    "previous_page_url": null,
    "url": "https://accounts.twilio.com/v1/Credentials/PublicKeys?PageSize=50&Page=0"
  }
}
```


# Create Credential Public Key

Create a new Public Key Credential

```python
def create_credential_public_key(self,
                                public_key,
                                friendly_name=None,
                                account_sid=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `public_key` | `str` | Form, Required | A URL encoded representation of the public key. For example, `-----BEGIN PUBLIC KEY-----MIIBIjANB.pa9xQIDAQAB-----END PUBLIC KEY-----` |
| `friendly_name` | `str` | Form, Optional | A descriptive string that you create to describe the resource. It can be up to 64 characters long. |
| `account_sid` | `str` | Form, Optional | The SID of the Subaccount that this Credential should be associated with. Must be a valid Subaccount of the account issuing the request<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^AC[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`CredentialPublicKey`](../../doc/models/credential-public-key.md).

## Example Usage

```python
public_key = 'public_key'

friendly_name = 'friendly_name'

account_sid = 'ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

result = accounts_v_1_public_key_api.create_credential_public_key(
    public_key,
    friendly_name=friendly_name,
    account_sid=account_sid
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
  "date_created": "2015-07-31T04:00:00Z",
  "date_updated": "2015-07-31T04:00:00Z",
  "friendly_name": "friendly_name",
  "sid": "CRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "url": "https://accounts.twilio.com/v1/Credentials/PublicKeys/CRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
}
```


# Fetch Credential Public Key

Fetch the public key specified by the provided Credential Sid

```python
def fetch_credential_public_key(self,
                               sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sid` | `str` | Template, Required | The Twilio-provided string that uniquely identifies the PublicKey resource to fetch.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^CR[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`CredentialPublicKey`](../../doc/models/credential-public-key.md).

## Example Usage

```python
sid = 'Sid8'

result = accounts_v_1_public_key_api.fetch_credential_public_key(sid)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "date_created": "2015-07-31T04:00:00Z",
  "date_updated": "2015-07-31T04:00:00Z",
  "friendly_name": "friendly_name",
  "sid": "CRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "url": "https://accounts.twilio.com/v1/Credentials/PublicKeys/CRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
}
```


# Update Credential Public Key

Modify the properties of a given Account

```python
def update_credential_public_key(self,
                                sid,
                                friendly_name=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sid` | `str` | Template, Required | The Twilio-provided string that uniquely identifies the PublicKey resource to update.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^CR[0-9a-fA-F]{32}$` |
| `friendly_name` | `str` | Form, Optional | A descriptive string that you create to describe the resource. It can be up to 64 characters long. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`CredentialPublicKey`](../../doc/models/credential-public-key.md).

## Example Usage

```python
sid = 'Sid8'

friendly_name = 'friendly_name'

result = accounts_v_1_public_key_api.update_credential_public_key(
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
  "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "date_created": "2015-07-31T04:00:00Z",
  "date_updated": "2015-07-31T04:00:00Z",
  "friendly_name": "friendly_name",
  "sid": "CRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "url": "https://accounts.twilio.com/v1/Credentials/PublicKeys/CRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
}
```


# Delete Credential Public Key

Delete a Credential from your account

```python
def delete_credential_public_key(self,
                                sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sid` | `str` | Template, Required | The Twilio-provided string that uniquely identifies the PublicKey resource to delete.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^CR[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```python
sid = 'Sid8'

result = accounts_v_1_public_key_api.delete_credential_public_key(sid)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

