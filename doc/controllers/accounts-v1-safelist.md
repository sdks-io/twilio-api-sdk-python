# Accounts V1 Safelist

```python
accounts_v_1_safelist_api = client.accounts_v_1_safelist
```

## Class Name

`AccountsV1SafelistApi`

## Methods

* [Create Safelist](../../doc/controllers/accounts-v1-safelist.md#create-safelist)
* [Fetch Safelist](../../doc/controllers/accounts-v1-safelist.md#fetch-safelist)
* [Delete Safelist](../../doc/controllers/accounts-v1-safelist.md#delete-safelist)


# Create Safelist

Add a new phone number or phone number 1k prefix to SafeList.

```python
def create_safelist(self,
                   phone_number)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `phone_number` | `str` | Form, Required | The phone number or phone number 1k prefix to be added in SafeList. Phone numbers must be in [E.164 format](https://www.twilio.com/docs/glossary/what-e164). |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Safelist`](../../doc/models/safelist.md).

## Example Usage

```python
phone_number = '+18001234567'

result = accounts_v_1_safelist_api.create_safelist(phone_number)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "sid": "GNaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "phone_number": "+18001234567"
}
```


# Fetch Safelist

Check if a phone number or phone number 1k prefix exists in SafeList.

```python
def fetch_safelist(self,
                  phone_number=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `phone_number` | `str` | Query, Optional | The phone number or phone number 1k prefix to be fetched from SafeList. Phone numbers must be in [E.164 format](https://www.twilio.com/docs/glossary/what-e164). |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Safelist`](../../doc/models/safelist.md).

## Example Usage

```python
phone_number = '+18001234567'

result = accounts_v_1_safelist_api.fetch_safelist(
    phone_number=phone_number
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "sid": "GNaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "phone_number": "+18001234567"
}
```


# Delete Safelist

Remove a phone number or phone number 1k prefix from SafeList.

```python
def delete_safelist(self,
                   phone_number=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `phone_number` | `str` | Query, Optional | The phone number or phone number 1k prefix to be removed from SafeList. Phone numbers must be in [E.164 format](https://www.twilio.com/docs/glossary/what-e164). |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```python
phone_number = '+18001234567'

result = accounts_v_1_safelist_api.delete_safelist(
    phone_number=phone_number
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

