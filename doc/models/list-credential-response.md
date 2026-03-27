
# List Credential Response

*This model accepts additional fields of type Any.*

## Structure

`ListCredentialResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `credentials` | [`List[Credential]`](../../doc/models/credential.md) | Optional | - |
| `meta` | [`Meta`](../../doc/models/meta.md) | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "credentials": [
    {
      "sid": "sid2",
      "account_sid": "account_sid2",
      "friendly_name": "friendly_name8",
      "type": "fcm",
      "sandbox": "sandbox6",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "sid": "sid2",
      "account_sid": "account_sid2",
      "friendly_name": "friendly_name8",
      "type": "fcm",
      "sandbox": "sandbox6",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "sid": "sid2",
      "account_sid": "account_sid2",
      "friendly_name": "friendly_name8",
      "type": "fcm",
      "sandbox": "sandbox6",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "meta": {
    "first_page_url": "first_page_url0",
    "key": "key2",
    "next_page_url": "next_page_url4",
    "page": 240,
    "page_size": 56,
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

