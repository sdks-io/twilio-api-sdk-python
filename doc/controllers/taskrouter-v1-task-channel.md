# Taskrouter V1 Task Channel

```python
taskrouter_v_1_task_channel_api = client.taskrouter_v_1_task_channel
```

## Class Name

`TaskrouterV1TaskChannelApi`

## Methods

* [Fetch Task Channel](../../doc/controllers/taskrouter-v1-task-channel.md#fetch-task-channel)
* [Update Task Channel](../../doc/controllers/taskrouter-v1-task-channel.md#update-task-channel)
* [Delete Task Channel](../../doc/controllers/taskrouter-v1-task-channel.md#delete-task-channel)
* [List Task Channel](../../doc/controllers/taskrouter-v1-task-channel.md#list-task-channel)
* [Create Task Channel](../../doc/controllers/taskrouter-v1-task-channel.md#create-task-channel)


# Fetch Task Channel

Types of tasks

```python
def fetch_task_channel(self,
                      workspace_sid,
                      sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `workspace_sid` | `str` | Template, Required | The SID of the Workspace with the Task Channel to fetch.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `sid` | `str` | Template, Required | The SID of the Task Channel resource to fetch. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`TaskChannel`](../../doc/models/task-channel.md).

## Example Usage

```python
workspace_sid = 'WorkspaceSid0'

sid = 'Sid8'

result = taskrouter_v_1_task_channel_api.fetch_task_channel(
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
  "date_created": "2016-04-14T17:35:54Z",
  "date_updated": "2016-04-14T17:35:54Z",
  "friendly_name": "Default",
  "sid": "TCaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "unique_name": "default",
  "url": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/TaskChannels/TCaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "workspace_sid": "WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "channel_optimized_routing": true,
  "links": {
    "workspace": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
  }
}
```


# Update Task Channel

Types of tasks

```python
def update_task_channel(self,
                       workspace_sid,
                       sid,
                       friendly_name=None,
                       channel_optimized_routing=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `workspace_sid` | `str` | Template, Required | The SID of the Workspace with the Task Channel to update.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `sid` | `str` | Template, Required | The SID of the Task Channel resource to update. |
| `friendly_name` | `str` | Form, Optional | A descriptive string that you create to describe the Task Channel. It can be up to 64 characters long. |
| `channel_optimized_routing` | `bool` | Form, Optional | Whether the TaskChannel should prioritize Workers that have been idle. If `true`, Workers that have been idle the longest are prioritized. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`TaskChannel`](../../doc/models/task-channel.md).

## Example Usage

```python
workspace_sid = 'WorkspaceSid0'

sid = 'Sid8'

friendly_name = 'Outbound Voice'

channel_optimized_routing = True

result = taskrouter_v_1_task_channel_api.update_task_channel(
    workspace_sid,
    sid,
    friendly_name=friendly_name,
    channel_optimized_routing=channel_optimized_routing
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
  "workspace_sid": "WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "sid": "TCaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "friendly_name": "Default",
  "unique_name": "default",
  "date_created": "2016-04-14T17:35:54Z",
  "date_updated": "2016-04-14T17:35:54Z",
  "url": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/TaskChannels/TCaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "channel_optimized_routing": true,
  "links": {
    "workspace": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
  }
}
```


# Delete Task Channel

Types of tasks

```python
def delete_task_channel(self,
                       workspace_sid,
                       sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `workspace_sid` | `str` | Template, Required | The SID of the Workspace with the Task Channel to delete.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `sid` | `str` | Template, Required | The SID of the Task Channel resource to delete. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```python
workspace_sid = 'WorkspaceSid0'

sid = 'Sid8'

result = taskrouter_v_1_task_channel_api.delete_task_channel(
    workspace_sid,
    sid
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# List Task Channel

Types of tasks

```python
def list_task_channel(self,
                     workspace_sid,
                     page_size=None,
                     page=None,
                     page_token=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `workspace_sid` | `str` | Template, Required | The SID of the Workspace with the Task Channel to read.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `page_size` | `int` | Query, Optional | How many resources to return in each list page. The default is 50, and the maximum is 1000.<br><br>**Constraints**: `>= 1`, `<= 1000` |
| `page` | `int` | Query, Optional | The page index. This value is simply for client state.<br><br>**Constraints**: `>= 0` |
| `page_token` | `str` | Query, Optional | The page token. This is provided by the API. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ListTaskChannelResponse`](../../doc/models/list-task-channel-response.md).

## Example Usage

```python
workspace_sid = 'WorkspaceSid0'

result = taskrouter_v_1_task_channel_api.list_task_channel(workspace_sid)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "channels": [
    {
      "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "date_created": "2016-04-14T17:35:54Z",
      "date_updated": "2016-04-14T17:35:54Z",
      "friendly_name": "Default",
      "sid": "TCaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "unique_name": "default",
      "url": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/TaskChannels/TCaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "workspace_sid": "WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "channel_optimized_routing": true,
      "links": {
        "workspace": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
      }
    }
  ],
  "meta": {
    "first_page_url": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/TaskChannels?PageSize=50&Page=0",
    "key": "channels",
    "next_page_url": null,
    "page": 0,
    "page_size": 50,
    "previous_page_url": null,
    "url": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/TaskChannels?PageSize=50&Page=0"
  }
}
```


# Create Task Channel

Types of tasks

```python
def create_task_channel(self,
                       workspace_sid,
                       friendly_name,
                       unique_name,
                       channel_optimized_routing=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `workspace_sid` | `str` | Template, Required | The SID of the Workspace that the new Task Channel belongs to.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `friendly_name` | `str` | Form, Required | A descriptive string that you create to describe the Task Channel. It can be up to 64 characters long. |
| `unique_name` | `str` | Form, Required | An application-defined string that uniquely identifies the Task Channel, such as `voice` or `sms`. |
| `channel_optimized_routing` | `bool` | Form, Optional | Whether the Task Channel should prioritize Workers that have been idle. If `true`, Workers that have been idle the longest are prioritized. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`TaskChannel`](../../doc/models/task-channel.md).

## Example Usage

```python
workspace_sid = 'WorkspaceSid0'

friendly_name = 'Outbound Voice'

unique_name = 'ovoice'

result = taskrouter_v_1_task_channel_api.create_task_channel(
    workspace_sid,
    friendly_name,
    unique_name
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
  "workspace_sid": "WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "sid": "TCaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "friendly_name": "Outbound Voice",
  "unique_name": "ovoice",
  "date_created": "2016-04-14T17:35:54Z",
  "date_updated": "2016-04-14T17:35:54Z",
  "channel_optimized_routing": true,
  "url": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/TaskChannels/TCaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "links": {
    "workspace": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
  }
}
```

