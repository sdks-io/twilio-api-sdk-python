
# List Service Role Response

*This model accepts additional fields of type Any.*

## Structure

`ListServiceRoleResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `roles` | [`List[ServiceRole]`](../../doc/models/service-role.md) | Optional | - |
| `meta` | [`Meta`](../../doc/models/meta.md) | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "roles": [
    {
      "sid": "sid4",
      "account_sid": "account_sid8",
      "chat_service_sid": "chat_service_sid2",
      "friendly_name": "friendly_name8",
      "type": "conversation",
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

