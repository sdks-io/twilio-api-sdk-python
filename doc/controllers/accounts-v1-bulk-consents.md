# Accounts V1 Bulk Consents

```python
accounts_v_1_bulk_consents_api = client.accounts_v_1_bulk_consents
```

## Class Name

`AccountsV1BulkConsentsApi`


# Create Bulk Consents

```python
def create_bulk_consents(self,
                        items)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `items` | `List[Any]` | Form, Required | This is a list of objects that describes a contact's opt-in status. Each object contains the following fields: `contact_id`, which must be a string representing phone number in [E.164 format](https://www.twilio.com/docs/glossary/what-e164); `correlation_id`, a unique 32-character UUID used to uniquely map the request item with the response item; `sender_id`, which can be either a valid messaging service SID or a from phone number; `status`, a string representing the consent status. Can be one of [`opt-in`, `opt-out`]; `source`, a string indicating the medium through which the consent was collected. Can be one of [`website`, `offline`, `opt-in-message`, `opt-out-message`, `others`]; `date_of_consent`, an optional datetime string field in ISO-8601 format that captures the exact date and time when the user gave or revoked consent. If not provided, it will be empty. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`BulkConsents`](../../doc/models/bulk-consents.md).

## Example Usage

```python
items = [
    jsonpickle.decode('"{\\"contact_id\\":\\"+19999999999\\",\\"correlation_id\\":\\"ad388b5a46b33b874b0d41f7226db2ef\\",\\"sender_id\\":\\"MG00000000000000000000000000000001\\",\\"date_of_consent\\":\\"2025-02-28T10:05:27Z\\",\\"status\\":\\"opt-out\\",\\"source\\":\\"website\\"}"'),
    jsonpickle.decode('"{\\"contact_id\\":\\"+19\\",\\"correlation_id\\":\\"02520cfa6c432f0e3ec3a38c122d428d\\",\\"sender_id\\":\\"123456\\",\\"date_of_consent\\":\\"2025-03-25\\",\\"status\\":\\"opt-in\\",\\"source\\":\\"opt-in-message\\"}"')
]

result = accounts_v_1_bulk_consents_api.create_bulk_consents(items)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

