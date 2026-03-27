# Taskrouter V1 Event

```python
taskrouter_v_1_event_api = client.taskrouter_v_1_event
```

## Class Name

`TaskrouterV1EventApi`

## Methods

* [Fetch Event](../../doc/controllers/taskrouter-v1-event.md#fetch-event)
* [List Event](../../doc/controllers/taskrouter-v1-event.md#list-event)


# Fetch Event

```python
def fetch_event(self,
               workspace_sid,
               sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `workspace_sid` | `str` | Template, Required | The SID of the Workspace with the Event to fetch.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `sid` | `str` | Template, Required | The SID of the Event resource to fetch.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^EV[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Event`](../../doc/models/event.md).

## Example Usage

```python
workspace_sid = 'WorkspaceSid0'

sid = 'Sid8'

result = taskrouter_v_1_event_api.fetch_event(
    workspace_sid,
    sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# List Event

```python
def list_event(self,
              workspace_sid,
              end_date=None,
              event_type=None,
              minutes=None,
              reservation_sid=None,
              start_date=None,
              task_queue_sid=None,
              task_sid=None,
              worker_sid=None,
              workflow_sid=None,
              task_channel=None,
              sid=None,
              page_size=None,
              page=None,
              page_token=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `workspace_sid` | `str` | Template, Required | The SID of the Workspace with the Events to read. Returns only the Events that pertain to the specified Workspace.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `end_date` | `datetime` | Query, Optional | Only include Events that occurred on or before this date, specified in GMT as an [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) date-time. |
| `event_type` | `str` | Query, Optional | The type of Events to read. Returns only Events of the type specified. |
| `minutes` | `int` | Query, Optional | The period of events to read in minutes. Returns only Events that occurred since this many minutes in the past. The default is `15` minutes. Task Attributes for Events occuring more 43,200 minutes ago will be redacted. |
| `reservation_sid` | `str` | Query, Optional | The SID of the Reservation with the Events to read. Returns only Events that pertain to the specified Reservation.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WR[0-9a-fA-F]{32}$` |
| `start_date` | `datetime` | Query, Optional | Only include Events from on or after this date and time, specified in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format. Task Attributes for Events older than 30 days will be redacted. |
| `task_queue_sid` | `str` | Query, Optional | The SID of the TaskQueue with the Events to read. Returns only the Events that pertain to the specified TaskQueue.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WQ[0-9a-fA-F]{32}$` |
| `task_sid` | `str` | Query, Optional | The SID of the Task with the Events to read. Returns only the Events that pertain to the specified Task.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WT[0-9a-fA-F]{32}$` |
| `worker_sid` | `str` | Query, Optional | The SID of the Worker with the Events to read. Returns only the Events that pertain to the specified Worker.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WK[0-9a-fA-F]{32}$` |
| `workflow_sid` | `str` | Query, Optional | The SID of the Workflow with the Events to read. Returns only the Events that pertain to the specified Workflow.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WW[0-9a-fA-F]{32}$` |
| `task_channel` | `str` | Query, Optional | The TaskChannel with the Events to read. Returns only the Events that pertain to the specified TaskChannel. |
| `sid` | `str` | Query, Optional | The SID of the Event resource to read.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^EV[0-9a-fA-F]{32}$` |
| `page_size` | `int` | Query, Optional | How many resources to return in each list page. The default is 50, and the maximum is 1000.<br><br>**Constraints**: `>= 1`, `<= 1000` |
| `page` | `int` | Query, Optional | The page index. This value is simply for client state.<br><br>**Constraints**: `>= 0` |
| `page_token` | `str` | Query, Optional | The page token. This is provided by the API. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ListEventResponse`](../../doc/models/list-event-response.md).

## Example Usage

```python
workspace_sid = 'WorkspaceSid0'

end_date = dateutil.parser.parse('01/03/2008 00:00:00')

event_type = 'reservation.created'

reservation_sid = 'WRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

start_date = dateutil.parser.parse('01/02/2008 00:00:00')

task_queue_sid = 'WQaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

task_sid = 'WTaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

worker_sid = 'WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

workflow_sid = 'WWaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

result = taskrouter_v_1_event_api.list_event(
    workspace_sid,
    end_date=end_date,
    event_type=event_type,
    reservation_sid=reservation_sid,
    start_date=start_date,
    task_queue_sid=task_queue_sid,
    task_sid=task_sid,
    worker_sid=worker_sid,
    workflow_sid=workflow_sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

