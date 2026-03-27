# Taskrouter V1 Task Queue Cumulative Statistics

```python
taskrouter_v_1_task_queue_cumulative_statistics_api = client.taskrouter_v_1_task_queue_cumulative_statistics
```

## Class Name

`TaskrouterV1TaskQueueCumulativeStatisticsApi`


# Fetch Task Queue Cumulative Statistics

```python
def fetch_task_queue_cumulative_statistics(self,
                                          workspace_sid,
                                          task_queue_sid,
                                          end_date=None,
                                          minutes=None,
                                          start_date=None,
                                          task_channel=None,
                                          split_by_wait_time=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `workspace_sid` | `str` | Template, Required | The SID of the Workspace with the TaskQueue to fetch.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `task_queue_sid` | `str` | Template, Required | The SID of the TaskQueue for which to fetch statistics.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WQ[0-9a-fA-F]{32}$` |
| `end_date` | `datetime` | Query, Optional | Only calculate statistics from this date and time and earlier, specified in GMT as an [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) date-time. |
| `minutes` | `int` | Query, Optional | Only calculate statistics since this many minutes in the past. The default is 15 minutes. |
| `start_date` | `datetime` | Query, Optional | Only calculate statistics from this date and time and later, specified in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format. |
| `task_channel` | `str` | Query, Optional | Only calculate cumulative statistics on this TaskChannel. Can be the TaskChannel's SID or its `unique_name`, such as `voice`, `sms`, or `default`. |
| `split_by_wait_time` | `str` | Query, Optional | A comma separated list of values that describes the thresholds, in seconds, to calculate statistics on. For each threshold specified, the number of Tasks canceled and reservations accepted above and below the specified thresholds in seconds are computed. TaskRouter will calculate statistics on up to 10,000 Tasks/Reservations for any given threshold. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`TaskQueueCumulative`](../../doc/models/task-queue-cumulative.md).

## Example Usage

```python
workspace_sid = 'WorkspaceSid0'

task_queue_sid = 'TaskQueueSid8'

end_date = dateutil.parser.parse('07/30/2015 20:00:00')

start_date = dateutil.parser.parse('07/30/2015 20:00:00')

result = taskrouter_v_1_task_queue_cumulative_statistics_api.fetch_task_queue_cumulative_statistics(
    workspace_sid,
    task_queue_sid,
    end_date=end_date,
    start_date=start_date
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

