
# List Service Binding Response

*This model accepts additional fields of type Any.*

## Structure

`ListServiceBindingResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `bindings` | [`List[ServiceBinding]`](../../doc/models/service-binding.md) | Optional | - |
| `meta` | [`Meta`](../../doc/models/meta.md) | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "bindings": [
    {
      "sid": "sid0",
      "account_sid": "account_sid4",
      "chat_service_sid": "chat_service_sid8",
      "credential_sid": "credential_sid8",
      "date_created": "2016-03-13T12:52:32.123Z",
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

