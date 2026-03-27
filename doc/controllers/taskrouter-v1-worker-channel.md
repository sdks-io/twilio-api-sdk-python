# Taskrouter V1 Worker Channel

```python
taskrouter_v_1_worker_channel_api = client.taskrouter_v_1_worker_channel
```

## Class Name

`TaskrouterV1WorkerChannelApi`

## Methods

* [List Worker Channel](../../doc/controllers/taskrouter-v1-worker-channel.md#list-worker-channel)
* [Fetch Worker Channel](../../doc/controllers/taskrouter-v1-worker-channel.md#fetch-worker-channel)
* [Update Worker Channel](../../doc/controllers/taskrouter-v1-worker-channel.md#update-worker-channel)


# List Worker Channel

```python
def list_worker_channel(self,
                       workspace_sid,
                       worker_sid,
                       page_size=None,
                       page=None,
                       page_token=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `workspace_sid` | `str` | Template, Required | The SID of the Workspace with the WorkerChannels to read.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `worker_sid` | `str` | Template, Required | The SID of the Worker with the WorkerChannels to read.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WK[0-9a-fA-F]{32}$` |
| `page_size` | `int` | Query, Optional | How many resources to return in each list page. The default is 50, and the maximum is 1000.<br><br>**Constraints**: `>= 1`, `<= 1000` |
| `page` | `int` | Query, Optional | The page index. This value is simply for client state.<br><br>**Constraints**: `>= 0` |
| `page_token` | `str` | Query, Optional | The page token. This is provided by the API. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ListWorkerChannelResponse`](../../doc/models/list-worker-channel-response.md).

## Example Usage

```python
workspace_sid = 'WorkspaceSid0'

worker_sid = 'WorkerSid0'

result = taskrouter_v_1_worker_channel_api.list_worker_channel(
    workspace_sid,
    worker_sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "meta": {
    "first_page_url": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Channels?PageSize=50&Page=0",
    "key": "channels",
    "next_page_url": null,
    "page": 0,
    "page_size": 50,
    "previous_page_url": null,
    "url": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Channels?PageSize=50&Page=0"
  },
  "channels": [
    {
      "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "assigned_tasks": 0,
      "available": true,
      "available_capacity_percentage": 100,
      "configured_capacity": 1,
      "date_created": "2016-04-14T17:35:54Z",
      "date_updated": "2016-04-14T17:35:54Z",
      "sid": "WCaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "task_channel_sid": "TCaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "task_channel_unique_name": "default",
      "url": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Channels/WCaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "worker_sid": "WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "workspace_sid": "WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
    }
  ]
}
```


# Fetch Worker Channel

```python
def fetch_worker_channel(self,
                        workspace_sid,
                        worker_sid,
                        sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `workspace_sid` | `str` | Template, Required | The SID of the Workspace with the WorkerChannel to fetch.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `worker_sid` | `str` | Template, Required | The SID of the Worker with the WorkerChannel to fetch.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WK[0-9a-fA-F]{32}$` |
| `sid` | `str` | Template, Required | The SID of the WorkerChannel to fetch. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`WorkerChannel`](../../doc/models/worker-channel.md).

## Example Usage

```python
workspace_sid = 'WorkspaceSid0'

worker_sid = 'WorkerSid0'

sid = 'Sid8'

result = taskrouter_v_1_worker_channel_api.fetch_worker_channel(
    workspace_sid,
    worker_sid,
    sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "assigned_tasks": 0,
  "available": true,
  "available_capacity_percentage": 100,
  "configured_capacity": 1,
  "date_created": "2016-04-14T17:35:54Z",
  "date_updated": "2016-04-14T17:35:54Z",
  "sid": "WCaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "task_channel_sid": "TCaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "task_channel_unique_name": "default",
  "url": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Channels/WCaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "worker_sid": "WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "workspace_sid": "WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
}
```


# Update Worker Channel

```python
def update_worker_channel(self,
                         workspace_sid,
                         worker_sid,
                         sid,
                         capacity=None,
                         available=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `workspace_sid` | `str` | Template, Required | The SID of the Workspace with the WorkerChannel to update.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `worker_sid` | `str` | Template, Required | The SID of the Worker with the WorkerChannel to update.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WK[0-9a-fA-F]{32}$` |
| `sid` | `str` | Template, Required | The SID of the WorkerChannel to update. |
| `capacity` | `int` | Form, Optional | The total number of Tasks that the Worker should handle for the TaskChannel type. TaskRouter creates reservations for Tasks of this TaskChannel type up to the specified capacity. If the capacity is 0, no new reservations will be created. |
| `available` | `bool` | Form, Optional | Whether the WorkerChannel is available. Set to `false` to prevent the Worker from receiving any new Tasks of this TaskChannel type. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`WorkerChannel`](../../doc/models/worker-channel.md).

## Example Usage

```python
workspace_sid = 'WorkspaceSid0'

worker_sid = 'WorkerSid0'

sid = 'Sid8'

capacity = 3

result = taskrouter_v_1_worker_channel_api.update_worker_channel(
    workspace_sid,
    worker_sid,
    sid,
    capacity=capacity
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "assigned_tasks": 0,
  "available": true,
  "available_capacity_percentage": 100,
  "configured_capacity": 3,
  "date_created": "2016-04-14T17:35:54Z",
  "date_updated": "2016-04-14T17:35:54Z",
  "sid": "WCaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "task_channel_sid": "TCaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "task_channel_unique_name": "default",
  "url": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Channels/WCaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "worker_sid": "WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "workspace_sid": "WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
}
```

