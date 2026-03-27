# Taskrouter V1 Task Queues Statistics

```python
taskrouter_v_1_task_queues_statistics_api = client.taskrouter_v_1_task_queues_statistics
```

## Class Name

`TaskrouterV1TaskQueuesStatisticsApi`


# List Task Queues Statistics

```python
def list_task_queues_statistics(self,
                               workspace_sid,
                               end_date=None,
                               friendly_name=None,
                               minutes=None,
                               start_date=None,
                               task_channel=None,
                               split_by_wait_time=None,
                               page_size=None,
                               page=None,
                               page_token=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `workspace_sid` | `str` | Template, Required | The SID of the Workspace with the TaskQueues to read.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `end_date` | `datetime` | Query, Optional | Only calculate statistics from this date and time and earlier, specified in GMT as an [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) date-time. |
| `friendly_name` | `str` | Query, Optional | The `friendly_name` of the TaskQueue statistics to read. |
| `minutes` | `int` | Query, Optional | Only calculate statistics since this many minutes in the past. The default is 15 minutes. |
| `start_date` | `datetime` | Query, Optional | Only calculate statistics from this date and time and later, specified in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format. |
| `task_channel` | `str` | Query, Optional | Only calculate statistics on this TaskChannel. Can be the TaskChannel's SID or its `unique_name`, such as `voice`, `sms`, or `default`. |
| `split_by_wait_time` | `str` | Query, Optional | A comma separated list of values that describes the thresholds, in seconds, to calculate statistics on. For each threshold specified, the number of Tasks canceled and reservations accepted above and below the specified thresholds in seconds are computed. |
| `page_size` | `int` | Query, Optional | How many resources to return in each list page. The default is 50, and the maximum is 1000.<br><br>**Constraints**: `>= 1`, `<= 1000` |
| `page` | `int` | Query, Optional | The page index. This value is simply for client state.<br><br>**Constraints**: `>= 0` |
| `page_token` | `str` | Query, Optional | The page token. This is provided by the API. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ListTaskQueuesStatisticsResponse`](../../doc/models/list-task-queues-statistics-response.md).

## Example Usage

```python
workspace_sid = 'WorkspaceSid0'

end_date = dateutil.parser.parse('01/02/2008 00:00:00')

friendly_name = 'friendly_name'

minutes = 1

start_date = dateutil.parser.parse('01/02/2008 00:00:00')

result = taskrouter_v_1_task_queues_statistics_api.list_task_queues_statistics(
    workspace_sid,
    end_date=end_date,
    friendly_name=friendly_name,
    minutes=minutes,
    start_date=start_date
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

