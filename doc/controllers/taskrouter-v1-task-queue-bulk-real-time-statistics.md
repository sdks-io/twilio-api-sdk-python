# Taskrouter V1 Task Queue Bulk Real Time Statistics

```python
taskrouter_v_1_task_queue_bulk_real_time_statistics_api = client.taskrouter_v_1_task_queue_bulk_real_time_statistics
```

## Class Name

`TaskrouterV1TaskQueueBulkRealTimeStatisticsApi`


# Create Task Queue Bulk Real Time Statistics

Fetch a Task Queue Real Time Statistics in bulk for the array of TaskQueue SIDs, support upto 50 in a request.

```python
def create_task_queue_bulk_real_time_statistics(self,
                                               workspace_sid,
                                               body=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `workspace_sid` | `str` | Template, Required | The unique SID identifier of the Workspace.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `body` | `Any` | Body, Optional | - |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`TaskQueueBulkRealTimeStatistics`](../../doc/models/task-queue-bulk-real-time-statistics.md).

## Example Usage

```python
workspace_sid = 'WorkspaceSid0'

result = taskrouter_v_1_task_queue_bulk_real_time_statistics_api.create_task_queue_bulk_real_time_statistics(workspace_sid)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "workspace_sid": "WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "url": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/TaskQueues/RealTimeStatistics",
  "task_queue_data": [
    {
      "task_queue_sid": "WQaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "longest_task_waiting_age": 100,
      "longest_task_waiting_sid": "WTaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "total_tasks": 100,
      "total_eligible_workers": 100,
      "total_available_workers": 100,
      "tasks_by_status": {
        "reserved": 0,
        "pending": 0,
        "assigned": 0,
        "wrapping": 0
      },
      "tasks_by_priority": {},
      "activity_statistics": [
        {
          "friendly_name": "Idle",
          "workers": 0,
          "sid": "WAaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
        },
        {
          "friendly_name": "Busy",
          "workers": 9,
          "sid": "WAaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
        },
        {
          "friendly_name": "Offline",
          "workers": 6,
          "sid": "WAaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
        },
        {
          "friendly_name": "Reserved",
          "workers": 0,
          "sid": "WAaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
        }
      ]
    }
  ],
  "task_queue_response_count": 100
}
```

