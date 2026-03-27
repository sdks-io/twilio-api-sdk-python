
# Event

*This model accepts additional fields of type Any.*

## Structure

`Event`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `account_sid` | `str` | Optional | The SID of the [Account](https://www.twilio.com/docs/iam/api/account) that created the Event resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^AC[0-9a-fA-F]{32}$` |
| `actor_sid` | `str` | Optional | The SID of the resource that triggered the event.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^[a-zA-Z]{2}[0-9a-fA-F]{32}$` |
| `actor_type` | `str` | Optional | The type of resource that triggered the event. |
| `actor_url` | `str` | Optional | The absolute URL of the resource that triggered the event. |
| `description` | `str` | Optional | A description of the event. |
| `event_data` | `Any` | Optional | Data about the event. For more information, see [Event types](https://www.twilio.com/docs/taskrouter/api/event#event-types). |
| `event_date` | `datetime` | Optional | The time the event was sent, specified in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format. |
| `event_date_ms` | `int` | Optional | The time the event was sent in milliseconds. |
| `event_type` | `str` | Optional | The identifier for the event. |
| `resource_sid` | `str` | Optional | The SID of the object the event is most relevant to, such as a TaskSid, ReservationSid, or a  WorkerSid.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^[a-zA-Z]{2}[0-9a-fA-F]{32}$` |
| `resource_type` | `str` | Optional | The type of object the event is most relevant to, such as a Task, Reservation, or a Worker). |
| `resource_url` | `str` | Optional | The URL of the resource the event is most relevant to. |
| `sid` | `str` | Optional | The unique string that we created to identify the Event resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^EV[0-9a-fA-F]{32}$` |
| `source` | `str` | Optional | Where the Event originated. |
| `source_ip_address` | `str` | Optional | The IP from which the Event originated. |
| `url` | `str` | Optional | The absolute URL of the Event resource. |
| `workspace_sid` | `str` | Optional | The SID of the Workspace that contains the Event.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "account_sid": "account_sid8",
  "actor_sid": "actor_sid4",
  "actor_type": "actor_type8",
  "actor_url": "actor_url6",
  "description": "description8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

