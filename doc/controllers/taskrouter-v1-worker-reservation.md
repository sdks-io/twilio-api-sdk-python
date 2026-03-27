# Taskrouter V1 Worker Reservation

```python
taskrouter_v_1_worker_reservation_api = client.taskrouter_v_1_worker_reservation
```

## Class Name

`TaskrouterV1WorkerReservationApi`

## Methods

* [List Worker Reservation](../../doc/controllers/taskrouter-v1-worker-reservation.md#list-worker-reservation)
* [Fetch Worker Reservation](../../doc/controllers/taskrouter-v1-worker-reservation.md#fetch-worker-reservation)
* [Update Worker Reservation](../../doc/controllers/taskrouter-v1-worker-reservation.md#update-worker-reservation)


# List Worker Reservation

Current and past reservations for a worker

```python
def list_worker_reservation(self,
                           workspace_sid,
                           worker_sid,
                           reservation_status=None,
                           page_size=None,
                           page=None,
                           page_token=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `workspace_sid` | `str` | Template, Required | The SID of the Workspace with the WorkerReservation resources to read.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `worker_sid` | `str` | Template, Required | The SID of the reserved Worker resource with the WorkerReservation resources to read.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WK[0-9a-fA-F]{32}$` |
| `reservation_status` | [`WorkerReservationStatus`](../../doc/models/worker-reservation-status.md) | Query, Optional | Returns the list of reservations for a worker with a specified ReservationStatus. Can be: `pending`, `accepted`, `rejected`, `timeout`, `canceled`, or `rescinded`. |
| `page_size` | `int` | Query, Optional | How many resources to return in each list page. The default is 50, and the maximum is 1000.<br><br>**Constraints**: `>= 1`, `<= 1000` |
| `page` | `int` | Query, Optional | The page index. This value is simply for client state.<br><br>**Constraints**: `>= 0` |
| `page_token` | `str` | Query, Optional | The page token. This is provided by the API. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ListWorkerReservationResponse`](../../doc/models/list-worker-reservation-response.md).

## Example Usage

```python
workspace_sid = 'WorkspaceSid0'

worker_sid = 'WorkerSid0'

result = taskrouter_v_1_worker_reservation_api.list_worker_reservation(
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
    "first_page_url": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Reservations?PageSize=50&Page=0",
    "key": "reservations",
    "next_page_url": null,
    "page": 0,
    "page_size": 50,
    "previous_page_url": null,
    "url": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Reservations?PageSize=50&Page=0"
  },
  "reservations": [
    {
      "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "date_created": "2014-05-14T10:50:02Z",
      "date_updated": "2014-05-15T16:03:42Z",
      "links": {
        "task": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Tasks/WTaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
        "worker": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
        "workspace": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
      },
      "reservation_status": "accepted",
      "sid": "WRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "task_sid": "WTaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "url": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Reservations/WRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "worker_name": "Doug",
      "worker_sid": "WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "workspace_sid": "WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
    }
  ]
}
```


# Fetch Worker Reservation

Current and past reservations for a worker

```python
def fetch_worker_reservation(self,
                            workspace_sid,
                            worker_sid,
                            sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `workspace_sid` | `str` | Template, Required | The SID of the Workspace with the WorkerReservation resource to fetch.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `worker_sid` | `str` | Template, Required | The SID of the reserved Worker resource with the WorkerReservation resource to fetch.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WK[0-9a-fA-F]{32}$` |
| `sid` | `str` | Template, Required | The SID of the WorkerReservation resource to fetch.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WR[0-9a-fA-F]{32}$` |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`WorkerReservation`](../../doc/models/worker-reservation.md).

## Example Usage

```python
workspace_sid = 'WorkspaceSid0'

worker_sid = 'WorkerSid0'

sid = 'Sid8'

result = taskrouter_v_1_worker_reservation_api.fetch_worker_reservation(
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
  "date_created": "2014-05-14T10:50:02Z",
  "date_updated": "2014-05-15T16:03:42Z",
  "links": {
    "task": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Tasks/WTaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
    "worker": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
    "workspace": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
  },
  "reservation_status": "accepted",
  "sid": "WRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "task_sid": "WTaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "url": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Reservations/WRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "worker_name": "Doug",
  "worker_sid": "WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "workspace_sid": "WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
}
```


# Update Worker Reservation

Current and past reservations for a worker

```python
def update_worker_reservation(self,
                             workspace_sid,
                             worker_sid,
                             sid,
                             if_match=None,
                             reservation_status=None,
                             worker_activity_sid=None,
                             instruction=None,
                             dequeue_post_work_activity_sid=None,
                             dequeue_from=None,
                             dequeue_record=None,
                             dequeue_timeout=None,
                             dequeue_to=None,
                             dequeue_status_callback_url=None,
                             call_from=None,
                             call_record=None,
                             call_timeout=None,
                             call_to=None,
                             call_url=None,
                             call_status_callback_url=None,
                             call_accept=None,
                             redirect_call_sid=None,
                             redirect_accept=None,
                             redirect_url=None,
                             to=None,
                             mfrom=None,
                             status_callback=None,
                             status_callback_method=None,
                             status_callback_event=None,
                             timeout=None,
                             record=None,
                             muted=None,
                             beep=None,
                             start_conference_on_enter=None,
                             end_conference_on_exit=None,
                             wait_url=None,
                             wait_method=None,
                             early_media=None,
                             max_participants=None,
                             conference_status_callback=None,
                             conference_status_callback_method=None,
                             conference_status_callback_event=None,
                             conference_record=None,
                             conference_trim=None,
                             recording_channels=None,
                             recording_status_callback=None,
                             recording_status_callback_method=None,
                             conference_recording_status_callback=None,
                             conference_recording_status_callback_method=None,
                             region=None,
                             sip_auth_username=None,
                             sip_auth_password=None,
                             dequeue_status_callback_event=None,
                             post_work_activity_sid=None,
                             end_conference_on_customer_exit=None,
                             beep_on_customer_entrance=None,
                             jitter_buffer_size=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `workspace_sid` | `str` | Template, Required | The SID of the Workspace with the WorkerReservation resources to update.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `worker_sid` | `str` | Template, Required | The SID of the reserved Worker resource with the WorkerReservation resources to update.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WK[0-9a-fA-F]{32}$` |
| `sid` | `str` | Template, Required | The SID of the WorkerReservation resource to update.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WR[0-9a-fA-F]{32}$` |
| `if_match` | `str` | Header, Optional | The If-Match HTTP request header |
| `reservation_status` | [`WorkerReservationStatus`](../../doc/models/worker-reservation-status.md) | Form, Optional | The current status of the reservation. Can be: `pending`, `accepted`, `rejected`, `timeout`, `canceled`, or `rescinded`. |
| `worker_activity_sid` | `str` | Form, Optional | The new worker activity SID if rejecting a reservation.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WA[0-9a-fA-F]{32}$` |
| `instruction` | `str` | Form, Optional | The assignment instruction for the reservation. |
| `dequeue_post_work_activity_sid` | `str` | Form, Optional | The SID of the Activity resource to start after executing a Dequeue instruction.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WA[0-9a-fA-F]{32}$` |
| `dequeue_from` | `str` | Form, Optional | The caller ID of the call to the worker when executing a Dequeue instruction. |
| `dequeue_record` | `str` | Form, Optional | Whether to record both legs of a call when executing a Dequeue instruction or which leg to record. |
| `dequeue_timeout` | `int` | Form, Optional | The timeout for call when executing a Dequeue instruction. |
| `dequeue_to` | `str` | Form, Optional | The contact URI of the worker when executing a Dequeue instruction. Can be the URI of the Twilio Client, the SIP URI for Programmable SIP, or the [E.164](https://www.twilio.com/docs/glossary/what-e164) formatted phone number, depending on the destination. |
| `dequeue_status_callback_url` | `str` | Form, Optional | The callback URL for completed call event when executing a Dequeue instruction. |
| `call_from` | `str` | Form, Optional | The Caller ID of the outbound call when executing a Call instruction. |
| `call_record` | `str` | Form, Optional | Whether to record both legs of a call when executing a Call instruction. |
| `call_timeout` | `int` | Form, Optional | The timeout for a call when executing a Call instruction. |
| `call_to` | `str` | Form, Optional | The contact URI of the worker when executing a Call instruction. Can be the URI of the Twilio Client, the SIP URI for Programmable SIP, or the [E.164](https://www.twilio.com/docs/glossary/what-e164) formatted phone number, depending on the destination. |
| `call_url` | `str` | Form, Optional | TwiML URI executed on answering the worker's leg as a result of the Call instruction. |
| `call_status_callback_url` | `str` | Form, Optional | The URL to call for the completed call event when executing a Call instruction. |
| `call_accept` | `bool` | Form, Optional | Whether to accept a reservation when executing a Call instruction. |
| `redirect_call_sid` | `str` | Form, Optional | The Call SID of the call parked in the queue when executing a Redirect instruction.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^CA[0-9a-fA-F]{32}$` |
| `redirect_accept` | `bool` | Form, Optional | Whether the reservation should be accepted when executing a Redirect instruction. |
| `redirect_url` | `str` | Form, Optional | TwiML URI to redirect the call to when executing the Redirect instruction. |
| `to` | `str` | Form, Optional | The Contact URI of the worker when executing a Conference instruction. Can be the URI of the Twilio Client, the SIP URI for Programmable SIP, or the [E.164](https://www.twilio.com/docs/glossary/what-e164) formatted phone number, depending on the destination. |
| `mfrom` | `str` | Form, Optional | The caller ID of the call to the worker when executing a Conference instruction. |
| `status_callback` | `str` | Form, Optional | The URL we should call using the `status_callback_method` to send status information to your application. |
| `status_callback_method` | [`ConfigurationWebhookMethod`](../../doc/models/configuration-webhook-method.md) | Form, Optional | The HTTP method we should use to call `status_callback`. Can be: `POST` or `GET` and the default is `POST`. |
| `status_callback_event` | [`List[WorkerReservationCallStatus]`](../../doc/models/worker-reservation-call-status.md) | Form, Optional | The call progress events that we will send to `status_callback`. Can be: `initiated`, `ringing`, `answered`, or `completed`. |
| `timeout` | `int` | Form, Optional | The timeout for a call when executing a Conference instruction. |
| `record` | `bool` | Form, Optional | Whether to record the participant and their conferences, including the time between conferences. Can be `true` or `false` and the default is `false`. |
| `muted` | `bool` | Form, Optional | Whether the agent is muted in the conference. Defaults to `false`. |
| `beep` | `str` | Form, Optional | Whether to play a notification beep when the participant joins or when to play a beep. Can be: `true`, `false`, `onEnter`, or `onExit`. The default value is `true`. |
| `start_conference_on_enter` | `bool` | Form, Optional | Whether to start the conference when the participant joins, if it has not already started. Can be: `true` or `false` and the default is `true`. If `false` and the conference has not started, the participant is muted and hears background music until another participant starts the conference. |
| `end_conference_on_exit` | `bool` | Form, Optional | Whether to end the conference when the agent leaves. |
| `wait_url` | `str` | Form, Optional | The URL we should call using the `wait_method` for the music to play while participants are waiting for the conference to start. The default value is the URL of our standard hold music. [Learn more about hold music](https://www.twilio.com/labs/twimlets/holdmusic). |
| `wait_method` | [`ConfigurationWebhookMethod`](../../doc/models/configuration-webhook-method.md) | Form, Optional | The HTTP method we should use to call `wait_url`. Can be `GET` or `POST` and the default is `POST`. When using a static audio file, this should be `GET` so that we can cache the file. |
| `early_media` | `bool` | Form, Optional | Whether to allow an agent to hear the state of the outbound call, including ringing or disconnect messages. The default is `true`. |
| `max_participants` | `int` | Form, Optional | The maximum number of participants allowed in the conference. Can be a positive integer from `2` to `250`. The default value is `250`. |
| `conference_status_callback` | `str` | Form, Optional | The URL we should call using the `conference_status_callback_method` when the conference events in `conference_status_callback_event` occur. Only the value set by the first participant to join the conference is used. Subsequent `conference_status_callback` values are ignored. |
| `conference_status_callback_method` | [`ConfigurationWebhookMethod`](../../doc/models/configuration-webhook-method.md) | Form, Optional | The HTTP method we should use to call `conference_status_callback`. Can be: `GET` or `POST` and defaults to `POST`. |
| `conference_status_callback_event` | [`List[WorkerReservationConferenceEvent]`](../../doc/models/worker-reservation-conference-event.md) | Form, Optional | The conference status events that we will send to `conference_status_callback`. Can be: `start`, `end`, `join`, `leave`, `mute`, `hold`, `speaker`. |
| `conference_record` | `str` | Form, Optional | Whether to record the conference the participant is joining or when to record the conference. Can be: `true`, `false`, `record-from-start`, and `do-not-record`. The default value is `false`. |
| `conference_trim` | `str` | Form, Optional | Whether to trim leading and trailing silence from your recorded conference audio files. Can be: `trim-silence` or `do-not-trim` and defaults to `trim-silence`. |
| `recording_channels` | `str` | Form, Optional | The recording channels for the final recording. Can be: `mono` or `dual` and the default is `mono`. |
| `recording_status_callback` | `str` | Form, Optional | The URL that we should call using the `recording_status_callback_method` when the recording status changes. |
| `recording_status_callback_method` | [`ConfigurationWebhookMethod`](../../doc/models/configuration-webhook-method.md) | Form, Optional | The HTTP method we should use when we call `recording_status_callback`. Can be: `GET` or `POST` and defaults to `POST`. |
| `conference_recording_status_callback` | `str` | Form, Optional | The URL we should call using the `conference_recording_status_callback_method` when the conference recording is available. |
| `conference_recording_status_callback_method` | [`ConfigurationWebhookMethod`](../../doc/models/configuration-webhook-method.md) | Form, Optional | The HTTP method we should use to call `conference_recording_status_callback`. Can be: `GET` or `POST` and defaults to `POST`. |
| `region` | `str` | Form, Optional | The [region](https://support.twilio.com/hc/en-us/articles/223132167-How-global-low-latency-routing-and-region-selection-work-for-conferences-and-Client-calls) where we should mix the recorded audio. Can be:`us1`, `us2`, `ie1`, `de1`, `sg1`, `br1`, `au1`, or `jp1`. |
| `sip_auth_username` | `str` | Form, Optional | The SIP username used for authentication. |
| `sip_auth_password` | `str` | Form, Optional | The SIP password for authentication. |
| `dequeue_status_callback_event` | `List[str]` | Form, Optional | The call progress events sent via webhooks as a result of a Dequeue instruction. |
| `post_work_activity_sid` | `str` | Form, Optional | The new worker activity SID after executing a Conference instruction.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WA[0-9a-fA-F]{32}$` |
| `end_conference_on_customer_exit` | `bool` | Form, Optional | Whether to end the conference when the customer leaves. |
| `beep_on_customer_entrance` | `bool` | Form, Optional | Whether to play a notification beep when the customer joins. |
| `jitter_buffer_size` | `str` | Form, Optional | The jitter buffer size for conference. Can be: `small`, `medium`, `large`, `off`. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`WorkerReservation`](../../doc/models/worker-reservation.md).

## Example Usage

```python
workspace_sid = 'WorkspaceSid0'

worker_sid = 'WorkerSid0'

sid = 'Sid8'

reservation_status = WorkerReservationStatus.ACCEPTED

result = taskrouter_v_1_worker_reservation_api.update_worker_reservation(
    workspace_sid,
    worker_sid,
    sid,
    reservation_status=reservation_status
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
  "date_created": "2014-05-14T10:50:02Z",
  "date_updated": "2014-05-15T16:03:42Z",
  "links": {
    "task": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Tasks/WTaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
    "worker": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
    "workspace": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
  },
  "reservation_status": "accepted",
  "sid": "WRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "task_sid": "WTaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "url": "https://taskrouter.twilio.com/v1/Workspaces/WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Workers/WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa/Reservations/WRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "worker_name": "Doug",
  "worker_sid": "WKaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "workspace_sid": "WSaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
}
```

