# Accounts V1 Secondary Auth Token

```python
accounts_v_1_secondary_auth_token_api = client.accounts_v_1_secondary_auth_token
```

## Class Name

`AccountsV1SecondaryAuthTokenApi`

## Methods

* [Create Secondary Auth Token](../../doc/controllers/accounts-v1-secondary-auth-token.md#create-secondary-auth-token)
* [Delete Secondary Auth Token](../../doc/controllers/accounts-v1-secondary-auth-token.md#delete-secondary-auth-token)


# Create Secondary Auth Token

Create a new secondary Auth Token

```python
def create_secondary_auth_token(self)
```

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`SecondaryAuthToken`](../../doc/models/secondary-auth-token.md).

## Example Usage

```python
result = accounts_v_1_secondary_auth_token_api.create_secondary_auth_token()

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
  "secondary_auth_token": "bbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb",
  "url": "https://accounts.twilio.com/v1/AuthTokens/Secondary"
}
```


# Delete Secondary Auth Token

Delete the secondary Auth Token from your account

```python
def delete_secondary_auth_token(self)
```

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```python
result = accounts_v_1_secondary_auth_token_api.delete_secondary_auth_token()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

