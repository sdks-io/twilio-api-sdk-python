
# List Service User Response

*This model accepts additional fields of type Any.*

## Structure

`ListServiceUserResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `users` | [`List[ServiceUser]`](../../doc/models/service-user.md) | Optional | - |
| `meta` | [`Meta`](../../doc/models/meta.md) | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "users": [
    {
      "sid": "sid2",
      "account_sid": "account_sid2",
      "chat_service_sid": "chat_service_sid6",
      "role_sid": "role_sid2",
      "identity": "identity0",
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

