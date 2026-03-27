# Taskrouter V1 Workspace Cumulative Statistics

```python
taskrouter_v_1_workspace_cumulative_statistics_api = client.taskrouter_v_1_workspace_cumulative_statistics
```

## Class Name

`TaskrouterV1WorkspaceCumulativeStatisticsApi`


# Fetch Workspace Cumulative Statistics

```python
def fetch_workspace_cumulative_statistics(self,
                                         workspace_sid,
                                         end_date=None,
                                         minutes=None,
                                         start_date=None,
                                         task_channel=None,
                                         split_by_wait_time=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `workspace_sid` | `str` | Template, Required | The SID of the Workspace to fetch.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `end_date` | `datetime` | Query, Optional | Only include usage that occurred on or before this date, specified in GMT as an [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) date-time. |
| `minutes` | `int` | Query, Optional | Only calculate statistics since this many minutes in the past. The default 15 minutes. This is helpful for displaying statistics for the last 15 minutes, 240 minutes (4 hours), and 480 minutes (8 hours) to see trends. |
| `start_date` | `datetime` | Query, Optional | Only calculate statistics from this date and time and later, specified in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format. |
| `task_channel` | `str` | Query, Optional | Only calculate cumulative statistics on this TaskChannel. Can be the TaskChannel's SID or its `unique_name`, such as `voice`, `sms`, or `default`. |
| `split_by_wait_time` | `str` | Query, Optional | A comma separated list of values that describes the thresholds, in seconds, to calculate statistics on. For each threshold specified, the number of Tasks canceled and reservations accepted above and below the specified thresholds in seconds are computed. For example, `5,30` would show splits of Tasks that were canceled or accepted before and after 5 seconds and before and after 30 seconds. This can be used to show short abandoned Tasks or Tasks that failed to meet an SLA. TaskRouter will calculate statistics on up to 10,000 Tasks for any given threshold. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`WorkspaceCumulativeStatistics`](../../doc/models/workspace-cumulative-statistics.md).

## Example Usage

```python
workspace_sid = 'WorkspaceSid0'

end_date = dateutil.parser.parse('07/30/2015 20:00:00')

start_date = dateutil.parser.parse('07/30/2015 20:00:00')

result = taskrouter_v_1_workspace_cumulative_statistics_api.fetch_workspace_cumulative_statistics(
    workspace_sid,
    end_date=end_date,
    start_date=start_date
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

