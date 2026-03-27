
# List Task Queue Response

*This model accepts additional fields of type Any.*

## Structure

`ListTaskQueueResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `task_queues` | [`List[TaskQueue]`](../../doc/models/task-queue.md) | Optional | - |
| `meta` | [`Meta`](../../doc/models/meta.md) | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "task_queues": [
    {
      "account_sid": "account_sid6",
      "assignment_activity_sid": "assignment_activity_sid4",
      "assignment_activity_name": "assignment_activity_name2",
      "date_created": "2016-03-13T12:52:32.123Z",
      "date_updated": "2016-03-13T12:52:32.123Z",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "account_sid": "account_sid6",
      "assignment_activity_sid": "assignment_activity_sid4",
      "assignment_activity_name": "assignment_activity_name2",
      "date_created": "2016-03-13T12:52:32.123Z",
      "date_updated": "2016-03-13T12:52:32.123Z",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "account_sid": "account_sid6",
      "assignment_activity_sid": "assignment_activity_sid4",
      "assignment_activity_name": "assignment_activity_name2",
      "date_created": "2016-03-13T12:52:32.123Z",
      "date_updated": "2016-03-13T12:52:32.123Z",
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

