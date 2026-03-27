# Taskrouter V1 Workspace Real Time Statistics

```python
taskrouter_v_1_workspace_real_time_statistics_api = client.taskrouter_v_1_workspace_real_time_statistics
```

## Class Name

`TaskrouterV1WorkspaceRealTimeStatisticsApi`


# Fetch Workspace Real Time Statistics

```python
def fetch_workspace_real_time_statistics(self,
                                        workspace_sid,
                                        task_channel=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `workspace_sid` | `str` | Template, Required | The SID of the Workspace to fetch.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `task_channel` | `str` | Query, Optional | Only calculate real-time statistics on this TaskChannel. Can be the TaskChannel's SID or its `unique_name`, such as `voice`, `sms`, or `default`. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`WorkspaceRealTimeStatistics`](../../doc/models/workspace-real-time-statistics.md).

## Example Usage

```python
workspace_sid = 'WorkspaceSid0'

task_channel = 'voice'

result = taskrouter_v_1_workspace_real_time_statistics_api.fetch_workspace_real_time_statistics(
    workspace_sid,
    task_channel=task_channel
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

