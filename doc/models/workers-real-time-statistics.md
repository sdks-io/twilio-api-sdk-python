
# Workers Real Time Statistics

*This model accepts additional fields of type Any.*

## Structure

`WorkersRealTimeStatistics`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `account_sid` | `str` | Optional | The SID of the [Account](https://www.twilio.com/docs/iam/api/account) that created the Worker resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^AC[0-9a-fA-F]{32}$` |
| `activity_statistics` | `List[Any]` | Optional | The number of current Workers by Activity. |
| `total_workers` | `int` | Optional | The total number of Workers.<br><br>**Default**: `0` |
| `workspace_sid` | `str` | Optional | The SID of the Workspace that contains the Workers.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `url` | `str` | Optional | The absolute URL of the Workers statistics resource. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "total_workers": 0,
  "account_sid": "account_sid8",
  "activity_statistics": [
    {
      "key1": "val1",
      "key2": "val2"
    }
  ],
  "workspace_sid": "workspace_sid0",
  "url": "url6",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

