# Taskrouter V1 Worker

```python
taskrouter_v_1_worker_api = client.taskrouter_v_1_worker
```

## Class Name

`TaskrouterV1WorkerApi`

## Methods

* [List Worker](../../doc/controllers/taskrouter-v1-worker.md#list-worker)
* [Create Worker](../../doc/controllers/taskrouter-v1-worker.md#create-worker)
* [Fetch Worker](../../doc/controllers/taskrouter-v1-worker.md#fetch-worker)
* [Update Worker](../../doc/controllers/taskrouter-v1-worker.md#update-worker)
* [Delete Worker](../../doc/controllers/taskrouter-v1-worker.md#delete-worker)


# List Worker

```python
def list_worker(self,
               workspace_sid,
               activity_name=None,
               activity_sid=None,
               available=None,
               friendly_name=None,
               target_workers_expression=None,
               task_queue_name=None,
               task_queue_sid=None,
               ordering=None,
               page_size=None,
               page=None,
               page_token=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `workspace_sid` | `str` | Template, Required | The SID of the Workspace with the Workers to read.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `activity_name` | `str` | Query, Optional | The `activity_name` of the Worker resources to read. |
| `activity_sid` | `str` | Query, Optional | The `activity_sid` of the Worker resources to read.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WA[0-9a-fA-F]{32}$` |
| `available` | `str` | Query, Optional | Whether to return only Worker resources that are available or unavailable. Can be `true`, `1`, or `yes` to return Worker resources that are available, and `false`, or any value returns the Worker resources that are not available. |
| `friendly_name` | `str` | Query, Optional | The `friendly_name` of the Worker resources to read. |
| `target_workers_expression` | `str` | Query, Optional | Filter by Workers that would match an expression. In addition to fields in the workers' attributes, the expression can include the following worker fields: `sid`, `friendly_name`, `activity_sid`, or `activity_name` |
| `task_queue_name` | `str` | Query, Optional | The `friendly_name` of the TaskQueue that the Workers to read are eligible for. |
| `task_queue_sid` | `str` | Query, Optional | The SID of the TaskQueue that the Workers to read are eligible for.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WQ[0-9a-fA-F]{32}$` |
| `ordering` | `str` | Query, Optional | Sorting parameter for Workers |
| `page_size` | `int` | Query, Optional | How many resources to return in each list page. The default is 50, and the maximum is 1000.<br><br>**Constraints**: `>= 1`, `<= 1000` |
| `page` | `int` | Query, Optional | The page index. This value is simply for client state.<br><br>**Constraints**: `>= 0` |
| `page_token` | `str` | Query, Optional | The page token. This is provided by the API. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ListWorkerResponse`](../../doc/models/list-worker-response.md).

## Example Usage

```python
workspace_sid = 'WorkspaceSid0'

activity_name = 'activity_name'

activity_sid = 'WAaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

available = 'available'

friendly_name = 'friendly_name'

target_workers_expression = 'target_workers_expression'

task_queue_name = 'task_queue_name'

task_queue_sid = 'WQaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

result = taskrouter_v_1_worker_api.list_worker(
    workspace_sid,
    activity_name=activity_name,
    activity_sid=activity_sid,
    available=available,
    friendly_name=friendly_name,
    target_workers_expression=target_workers_expression,
    task_queue_name=task_queue_name,
    task_queue_sid=task_queue_sid
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
    "page": 0,
    "page_size": 50,
    "first_page_url": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers?Available=available&TargetWorkersExpression=target_workers_expression&TaskQueueName=task_queue_name&ActivityName=activity_name&ActivitySid=WAaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa&TaskQueueSid=WQaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa&FriendlyName=friendly_name&PageSize=50&Page=0",
    "previous_page_url": null,
    "url": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers?Available=available&TargetWorkersExpression=target_workers_expression&TaskQueueName=task_queue_name&ActivityName=activity_name&ActivitySid=WAaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa&TaskQueueSid=WQaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa&FriendlyName=friendly_name&PageSize=50&Page=0",
    "next_page_url": null,
    "key": "workers"
  },
  "workers": [
    {
      "sid": "WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "friendly_name": "testWorker",
      "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "activity_sid": "WAaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "activity_name": "Offline",
      "workspace_sid": "WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "attributes": "{}",
      "available": false,
      "date_created": "2017-05-30T23:05:29Z",
      "date_updated": "2017-05-30T23:05:29Z",
      "date_status_changed": "2017-05-30T23:05:29Z",
      "url": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "links": {
        "channels": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Channels",
        "activity": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Activities/WAaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
        "workspace": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
        "statistics": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/Statistics",
        "real_time_statistics": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/RealTimeStatistics",
        "cumulative_statistics": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/CumulativeStatistics",
        "worker_statistics": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Statistics",
        "worker_channels": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Channels",
        "reservations": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Reservations"
      }
    }
  ]
}
```


# Create Worker

```python
def create_worker(self,
                 workspace_sid,
                 friendly_name,
                 activity_sid=None,
                 attributes=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `workspace_sid` | `str` | Template, Required | The SID of the Workspace that the new Worker belongs to.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `friendly_name` | `str` | Form, Required | A descriptive string that you create to describe the new Worker. It can be up to 64 characters long. |
| `activity_sid` | `str` | Form, Optional | The SID of a valid Activity that will describe the new Worker's initial state. See [Activities](https://www.twilio.com/docs/taskrouter/api/activity) for more information. If not provided, the new Worker's initial state is the `default_activity_sid` configured on the Workspace.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WA[0-9a-fA-F]{32}$` |
| `attributes` | `str` | Form, Optional | A valid JSON string that describes the new Worker. For example: `{ "email": "Bob@example.com", "phone": "+5095551234" }`. This data is passed to the `assignment_callback_url` when TaskRouter assigns a Task to the Worker. Defaults to {}. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Worker`](../../doc/models/worker.md).

## Example Usage

```python
workspace_sid = 'WorkspaceSid0'

friendly_name = 'friendly_name'

activity_sid = 'WAaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

attributes = 'attributes'

result = taskrouter_v_1_worker_api.create_worker(
    workspace_sid,
    friendly_name,
    activity_sid=activity_sid,
    attributes=attributes
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "sid": "WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "friendly_name": "NewWorker",
  "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "activity_sid": "WAaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "activity_name": "Offline",
  "workspace_sid": "WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "attributes": "{}",
  "available": false,
  "date_created": "2017-05-30T23:19:38Z",
  "date_updated": "2017-05-30T23:19:38Z",
  "date_status_changed": "2017-05-30T23:19:38Z",
  "url": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "links": {
    "channels": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Channels",
    "activity": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Activities/WAaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
    "workspace": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
    "statistics": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/Statistics",
    "real_time_statistics": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/RealTimeStatistics",
    "cumulative_statistics": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/CumulativeStatistics",
    "worker_statistics": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Statistics",
    "worker_channels": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Channels",
    "reservations": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Reservations"
  }
}
```


# Fetch Worker

```python
def fetch_worker(self,
                workspace_sid,
                sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `workspace_sid` | `str` | Template, Required | The SID of the Workspace with the Worker to fetch.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `sid` | `str` | Template, Required | The SID of the Worker resource to fetch.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WK[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Worker`](../../doc/models/worker.md).

## Example Usage

```python
workspace_sid = 'WorkspaceSid0'

sid = 'Sid8'

result = taskrouter_v_1_worker_api.fetch_worker(
    workspace_sid,
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
  "activity_name": "available",
  "activity_sid": "WAaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "attributes": "{}",
  "available": false,
  "date_created": "2017-05-30T23:32:39Z",
  "date_status_changed": "2017-05-30T23:32:39Z",
  "date_updated": "2017-05-30T23:32:39Z",
  "friendly_name": "NewWorker3",
  "sid": "WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "url": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "workspace_sid": "WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "links": {
    "channels": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Channels",
    "activity": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Activities/WAaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
    "workspace": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
    "statistics": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/Statistics",
    "real_time_statistics": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/RealTimeStatistics",
    "cumulative_statistics": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/CumulativeStatistics",
    "worker_statistics": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Statistics",
    "worker_channels": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Channels",
    "reservations": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Reservations"
  }
}
```


# Update Worker

```python
def update_worker(self,
                 workspace_sid,
                 sid,
                 if_match=None,
                 activity_sid=None,
                 attributes=None,
                 friendly_name=None,
                 reject_pending_reservations=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `workspace_sid` | `str` | Template, Required | The SID of the Workspace with the Worker to update.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `sid` | `str` | Template, Required | The SID of the Worker resource to update.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WK[0-9a-fA-F]{32}$` |
| `if_match` | `str` | Header, Optional | The If-Match HTTP request header |
| `activity_sid` | `str` | Form, Optional | The SID of a valid Activity that will describe the Worker's initial state. See [Activities](https://www.twilio.com/docs/taskrouter/api/activity) for more information.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WA[0-9a-fA-F]{32}$` |
| `attributes` | `str` | Form, Optional | The JSON string that describes the Worker. For example: `{ "email": "Bob@example.com", "phone": "+5095551234" }`. This data is passed to the `assignment_callback_url` when TaskRouter assigns a Task to the Worker. Defaults to {}. |
| `friendly_name` | `str` | Form, Optional | A descriptive string that you create to describe the Worker. It can be up to 64 characters long. |
| `reject_pending_reservations` | `bool` | Form, Optional | Whether to reject the Worker's pending reservations. This option is only valid if the Worker's new [Activity](https://www.twilio.com/docs/taskrouter/api/activity) resource has its `availability` property set to `False`. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Worker`](../../doc/models/worker.md).

## Example Usage

```python
workspace_sid = 'WorkspaceSid0'

sid = 'Sid8'

activity_sid = 'WAaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

attributes = 'attributes'

friendly_name = 'friendly_name'

result = taskrouter_v_1_worker_api.update_worker(
    workspace_sid,
    sid,
    activity_sid=activity_sid,
    attributes=attributes,
    friendly_name=friendly_name
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "sid": "WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "friendly_name": "blah",
  "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "activity_sid": "WAaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "activity_name": "Offline",
  "workspace_sid": "WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "attributes": "{}",
  "available": false,
  "date_created": "2017-05-30T23:32:22Z",
  "date_updated": "2017-05-31T00:05:57Z",
  "date_status_changed": "2017-05-30T23:32:22Z",
  "url": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "links": {
    "channels": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Channels",
    "activity": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Activities/WAaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
    "workspace": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
    "statistics": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/Statistics",
    "real_time_statistics": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/RealTimeStatistics",
    "cumulative_statistics": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/CumulativeStatistics",
    "worker_statistics": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Statistics",
    "worker_channels": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Channels",
    "reservations": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Reservations"
  }
}
```


# Delete Worker

```python
def delete_worker(self,
                 workspace_sid,
                 sid,
                 if_match=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `workspace_sid` | `str` | Template, Required | The SID of the Workspace with the Worker to delete.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `sid` | `str` | Template, Required | The SID of the Worker resource to delete.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WK[0-9a-fA-F]{32}$` |
| `if_match` | `str` | Header, Optional | The If-Match HTTP request header |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```python
workspace_sid = 'WorkspaceSid0'

sid = 'Sid8'

result = taskrouter_v_1_worker_api.delete_worker(
    workspace_sid,
    sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

