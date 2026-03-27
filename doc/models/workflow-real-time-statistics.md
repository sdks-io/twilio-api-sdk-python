
# Workflow Real Time Statistics

*This model accepts additional fields of type Any.*

## Structure

`WorkflowRealTimeStatistics`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `account_sid` | `str` | Optional | The SID of the [Account](https://www.twilio.com/docs/iam/api/account) that created the Workflow resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^AC[0-9a-fA-F]{32}$` |
| `longest_task_waiting_age` | `int` | Optional | The age of the longest waiting Task.<br><br>**Default**: `0` |
| `longest_task_waiting_sid` | `str` | Optional | The SID of the longest waiting Task.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WT[0-9a-fA-F]{32}$` |
| `tasks_by_priority` | `Any` | Optional | The number of Tasks by priority. For example: `{"0": "10", "99": "5"}` shows 10 Tasks at priority 0 and 5 at priority 99. |
| `tasks_by_status` | `Any` | Optional | The number of Tasks by their current status. For example: `{"pending": "1", "reserved": "3", "assigned": "2", "completed": "5"}`. |
| `total_tasks` | `int` | Optional | The total number of Tasks.<br><br>**Default**: `0` |
| `workflow_sid` | `str` | Optional | Returns the list of Tasks that are being controlled by the Workflow with the specified SID value.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WW[0-9a-fA-F]{32}$` |
| `workspace_sid` | `str` | Optional | The SID of the Workspace that contains the Workflow.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `url` | `str` | Optional | The absolute URL of the Workflow statistics resource. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "longest_task_waiting_age": 0,
  "total_tasks": 0,
  "account_sid": "account_sid6",
  "longest_task_waiting_sid": "longest_task_waiting_sid6",
  "tasks_by_priority": {
    "key1": "val1",
    "key2": "val2"
  },
  "tasks_by_status": {
    "key1": "val1",
    "key2": "val2"
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

