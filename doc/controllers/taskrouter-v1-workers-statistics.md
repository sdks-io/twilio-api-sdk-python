# Taskrouter V1 Workers Statistics

```python
taskrouter_v_1_workers_statistics_api = client.taskrouter_v_1_workers_statistics
```

## Class Name

`TaskrouterV1WorkersStatisticsApi`


# Fetch Worker Statistics

```python
def fetch_worker_statistics(self,
                           workspace_sid,
                           minutes=None,
                           start_date=None,
                           end_date=None,
                           task_queue_sid=None,
                           task_queue_name=None,
                           friendly_name=None,
                           task_channel=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `workspace_sid` | `str` | Template, Required | The SID of the Workspace with the Worker to fetch.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `minutes` | `int` | Query, Optional | Only calculate statistics since this many minutes in the past. The default 15 minutes. This is helpful for displaying statistics for the last 15 minutes, 240 minutes (4 hours), and 480 minutes (8 hours) to see trends. |
| `start_date` | `datetime` | Query, Optional | Only calculate statistics from this date and time and later, specified in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format. |
| `end_date` | `datetime` | Query, Optional | Only calculate statistics from this date and time and earlier, specified in GMT as an [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) date-time. |
| `task_queue_sid` | `str` | Query, Optional | The SID of the TaskQueue for which to fetch Worker statistics.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WQ[0-9a-fA-F]{32}$` |
| `task_queue_name` | `str` | Query, Optional | The `friendly_name` of the TaskQueue for which to fetch Worker statistics. |
| `friendly_name` | `str` | Query, Optional | Only include Workers with `friendly_name` values that match this parameter. |
| `task_channel` | `str` | Query, Optional | Only calculate statistics on this TaskChannel. Can be the TaskChannel's SID or its `unique_name`, such as `voice`, `sms`, or `default`. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`WorkerStatistics`](../../doc/models/worker-statistics.md).

## Example Usage

```python
workspace_sid = 'WorkspaceSid0'

minutes = 1

start_date = dateutil.parser.parse('01/02/2008 00:00:00')

end_date = dateutil.parser.parse('01/02/2008 00:00:00')

result = taskrouter_v_1_workers_statistics_api.fetch_worker_statistics(
    workspace_sid,
    minutes=minutes,
    start_date=start_date,
    end_date=end_date
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

