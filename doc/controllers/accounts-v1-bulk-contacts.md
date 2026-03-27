# Accounts V1 Bulk Contacts

```python
accounts_v_1_bulk_contacts_api = client.accounts_v_1_bulk_contacts
```

## Class Name

`AccountsV1BulkContactsApi`


# Create Bulk Contacts

```python
def create_bulk_contacts(self,
                        items)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `items` | `List[Any]` | Form, Required | A list of objects where each object represents a contact's details. Each object includes the following fields: `contact_id`, which must be a string representing phone number in [E.164 format](https://www.twilio.com/docs/glossary/what-e164); `correlation_id`, a unique 32-character UUID that maps the response to the original request; `country_iso_code`, a string representing the country using the ISO format (e.g., US for the United States); and `zip_code`, a string representing the postal code. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`BulkContacts`](../../doc/models/bulk-contacts.md).

## Example Usage

```python
items = [
    jsonpickle.decode('"{\\"contact_id\\":\\"+19999999999\\",\\"correlation_id\\":\\"ad388b5a46b33b874b0d41f7226db2eh\\",\\"country_iso_code\\":\\"US\\",\\"zip_code\\":\\"12345\\"}"'),
    jsonpickle.decode('"{\\"contact_id\\":\\"+19\\",\\"correlation_id\\":\\"02520cfa6c432f0e3ec3a38c122d428a\\",\\"country_iso_code\\":\\"US\\",\\"zip_code\\":\\"12345\\"}"')
]

result = accounts_v_1_bulk_contacts_api.create_bulk_contacts(items)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

