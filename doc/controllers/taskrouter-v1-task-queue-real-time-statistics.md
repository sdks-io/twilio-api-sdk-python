# Taskrouter V1 Task Queue Real Time Statistics

```python
taskrouter_v_1_task_queue_real_time_statistics_api = client.taskrouter_v_1_task_queue_real_time_statistics
```

## Class Name

`TaskrouterV1TaskQueueRealTimeStatisticsApi`


# Fetch Task Queue Real Time Statistics

```python
def fetch_task_queue_real_time_statistics(self,
                                         workspace_sid,
                                         task_queue_sid,
                                         task_channel=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `workspace_sid` | `str` | Template, Required | The SID of the Workspace with the TaskQueue to fetch.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `task_queue_sid` | `str` | Template, Required | The SID of the TaskQueue for which to fetch statistics.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WQ[0-9a-fA-F]{32}$` |
| `task_channel` | `str` | Query, Optional | The TaskChannel for which to fetch statistics. Can be the TaskChannel's SID or its `unique_name`, such as `voice`, `sms`, or `default`. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`TaskQueueRealTimeStatistics`](../../doc/models/task-queue-real-time-statistics.md).

## Example Usage

```python
workspace_sid = 'WorkspaceSid0'

task_queue_sid = 'TaskQueueSid8'

task_channel = 'voice'

result = taskrouter_v_1_task_queue_real_time_statistics_api.fetch_task_queue_real_time_statistics(
    workspace_sid,
    task_queue_sid,
    task_channel=task_channel
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

