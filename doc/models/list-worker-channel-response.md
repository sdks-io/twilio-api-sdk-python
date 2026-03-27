
# List Worker Channel Response

*This model accepts additional fields of type Any.*

## Structure

`ListWorkerChannelResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `channels` | [`List[WorkerChannel]`](../../doc/models/worker-channel.md) | Optional | - |
| `meta` | [`Meta`](../../doc/models/meta.md) | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "channels": [
    {
      "account_sid": "account_sid6",
      "assigned_tasks": 66,
      "available": false,
      "available_capacity_percentage": 34,
      "configured_capacity": 108,
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "account_sid": "account_sid6",
      "assigned_tasks": 66,
      "available": false,
      "available_capacity_percentage": 34,
      "configured_capacity": 108,
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "account_sid": "account_sid6",
      "assigned_tasks": 66,
      "available": false,
      "available_capacity_percentage": 34,
      "configured_capacity": 108,
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

