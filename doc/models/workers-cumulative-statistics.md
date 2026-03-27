
# Workers Cumulative Statistics

*This model accepts additional fields of type Any.*

## Structure

`WorkersCumulativeStatistics`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `account_sid` | `str` | Optional | The SID of the [Account](https://www.twilio.com/docs/iam/api/account) that created the Worker resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^AC[0-9a-fA-F]{32}$` |
| `start_time` | `datetime` | Optional | The beginning of the interval during which these statistics were calculated, in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format. |
| `end_time` | `datetime` | Optional | The end of the interval during which these statistics were calculated, in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format. |
| `activity_durations` | `List[Any]` | Optional | The minimum, average, maximum, and total time (in seconds) that Workers spent in each Activity. |
| `reservations_created` | `int` | Optional | The total number of Reservations that were created.<br><br>**Default**: `0` |
| `reservations_accepted` | `int` | Optional | The total number of Reservations that were accepted.<br><br>**Default**: `0` |
| `reservations_rejected` | `int` | Optional | The total number of Reservations that were rejected.<br><br>**Default**: `0` |
| `reservations_timed_out` | `int` | Optional | The total number of Reservations that were timed out.<br><br>**Default**: `0` |
| `reservations_canceled` | `int` | Optional | The total number of Reservations that were canceled.<br><br>**Default**: `0` |
| `reservations_rescinded` | `int` | Optional | The total number of Reservations that were rescinded.<br><br>**Default**: `0` |
| `workspace_sid` | `str` | Optional | The SID of the Workspace that contains the Workers.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `url` | `str` | Optional | The absolute URL of the Workers statistics resource. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "reservations_created": 0,
  "reservations_accepted": 0,
  "reservations_rejected": 0,
  "reservations_timed_out": 0,
  "reservations_canceled": 0,
  "reservations_rescinded": 0,
  "account_sid": "account_sid2",
  "start_time": "2016-03-13T12:52:32.123Z",
  "end_time": "2016-03-13T12:52:32.123Z",
  "activity_durations": [
    {
      "key1": "val1",
      "key2": "val2"
    }
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

