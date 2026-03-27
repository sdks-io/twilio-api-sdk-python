
# Task Queue Real Time Statistics

*This model accepts additional fields of type Any.*

## Structure

`TaskQueueRealTimeStatistics`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `account_sid` | `str` | Optional | The SID of the [Account](https://www.twilio.com/docs/iam/api/account) that created the TaskQueue resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^AC[0-9a-fA-F]{32}$` |
| `activity_statistics` | `List[Any]` | Optional | The number of current Workers by Activity. |
| `longest_task_waiting_age` | `int` | Optional | The age of the longest waiting Task.<br><br>**Default**: `0` |
| `longest_task_waiting_sid` | `str` | Optional | The SID of the longest waiting Task.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WT[0-9a-fA-F]{32}$` |
| `longest_relative_task_age_in_queue` | `int` | Optional | The relative age in the TaskQueue for the longest waiting Task. Calculation is based on the time when the Task entered the TaskQueue.<br><br>**Default**: `0` |
| `longest_relative_task_sid_in_queue` | `str` | Optional | The Task SID of the Task waiting in the TaskQueue the longest. Calculation is based on the time when the Task entered the TaskQueue.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WT[0-9a-fA-F]{32}$` |
| `task_queue_sid` | `str` | Optional | The SID of the TaskQueue from which these statistics were calculated.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WQ[0-9a-fA-F]{32}$` |
| `tasks_by_priority` | `Any` | Optional | The number of Tasks by priority. For example: `{"0": "10", "99": "5"}` shows 10 Tasks at priority 0 and 5 at priority 99. |
| `tasks_by_status` | `Any` | Optional | The number of Tasks by their current status. For example: `{"pending": "1", "reserved": "3", "assigned": "2", "completed": "5"}`. |
| `total_available_workers` | `int` | Optional | The total number of Workers in the TaskQueue with an `available` status. Workers with an `available` status may already have active interactions or may have none.<br><br>**Default**: `0` |
| `total_eligible_workers` | `int` | Optional | The total number of Workers eligible for Tasks in the TaskQueue, independent of their Activity state.<br><br>**Default**: `0` |
| `total_tasks` | `int` | Optional | The total number of Tasks.<br><br>**Default**: `0` |
| `workspace_sid` | `str` | Optional | The SID of the Workspace that contains the TaskQueue.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `url` | `str` | Optional | The absolute URL of the TaskQueue statistics resource. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "longest_task_waiting_age": 0,
  "longest_relative_task_age_in_queue": 0,
  "total_available_workers": 0,
  "total_eligible_workers": 0,
  "total_tasks": 0,
  "account_sid": "account_sid8",
  "activity_statistics": [
    {
      "key1": "val1",
      "key2": "val2"
    },
    {
      "key1": "val1",
      "key2": "val2"
    },
    {
      "key1": "val1",
      "key2": "val2"
    }
  ],
  "longest_task_waiting_sid": "longest_task_waiting_sid6",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

