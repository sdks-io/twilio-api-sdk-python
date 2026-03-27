# Taskrouter V1 Worker Statistics

```python
taskrouter_v_1_worker_statistics_api = client.taskrouter_v_1_worker_statistics
```

## Class Name

`TaskrouterV1WorkerStatisticsApi`


# Fetch Worker Instance Statistics

```python
def fetch_worker_instance_statistics(self,
                                    workspace_sid,
                                    worker_sid,
                                    minutes=None,
                                    start_date=None,
                                    end_date=None,
                                    task_channel=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `workspace_sid` | `str` | Template, Required | The SID of the Workspace with the WorkerChannel to fetch.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `worker_sid` | `str` | Template, Required | The SID of the Worker with the WorkerChannel to fetch.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WK[0-9a-fA-F]{32}$` |
| `minutes` | `int` | Query, Optional | Only calculate statistics since this many minutes in the past. The default 15 minutes. This is helpful for displaying statistics for the last 15 minutes, 240 minutes (4 hours), and 480 minutes (8 hours) to see trends. |
| `start_date` | `datetime` | Query, Optional | Only calculate statistics from this date and time and later, specified in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format. |
| `end_date` | `datetime` | Query, Optional | Only include usage that occurred on or before this date, specified in GMT as an [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) date-time. |
| `task_channel` | `str` | Query, Optional | Only calculate statistics on this TaskChannel. Can be the TaskChannel's SID or its `unique_name`, such as `voice`, `sms`, or `default`. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`WorkerInstanceStatistics`](../../doc/models/worker-instance-statistics.md).

## Example Usage

```python
workspace_sid = 'WorkspaceSid0'

worker_sid = 'WorkerSid0'

minutes = 1

start_date = dateutil.parser.parse('01/02/2008 00:00:00')

end_date = dateutil.parser.parse('01/02/2008 00:00:00')

result = taskrouter_v_1_worker_statistics_api.fetch_worker_instance_statistics(
    workspace_sid,
    worker_sid,
    minutes=minutes,
    start_date=start_date,
    end_date=end_date
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

