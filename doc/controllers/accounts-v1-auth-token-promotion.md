# Accounts V1 Auth Token Promotion

```python
accounts_v_1_auth_token_promotion_api = client.accounts_v_1_auth_token_promotion
```

## Class Name

`AccountsV1AuthTokenPromotionApi`


# Update Auth Token Promotion

Promote the secondary Auth Token to primary. After promoting the new token, all requests to Twilio using your old primary Auth Token will result in an error.

```python
def update_auth_token_promotion(self)
```

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`AuthTokenPromotion`](../../doc/models/auth-token-promotion.md).

## Example Usage

```python
result = accounts_v_1_auth_token_promotion_api.update_auth_token_promotion()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "auth_token": "bbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb",
  "date_created": "2015-07-31T04:00:00Z",
  "date_updated": "2015-07-31T04:00:00Z",
  "url": "https://accounts.twilio.com/v1/AuthTokens/Promote"
}
```

