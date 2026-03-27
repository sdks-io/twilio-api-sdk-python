
# Worker Statistics

*This model accepts additional fields of type Any.*

## Structure

`WorkerStatistics`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `realtime` | `Any` | Optional | An object that contains the real-time statistics for the Worker. |
| `cumulative` | `Any` | Optional | An object that contains the cumulative statistics for the Worker. |
| `account_sid` | `str` | Optional | The SID of the [Account](https://www.twilio.com/docs/iam/api/account) that created the Worker resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^AC[0-9a-fA-F]{32}$` |
| `workspace_sid` | `str` | Optional | The SID of the Workspace that contains the Worker.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `url` | `str` | Optional | The absolute URL of the Worker statistics resource. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "realtime": {
    "key1": "val1",
    "key2": "val2"
  },
  "cumulative": {
    "key1": "val1",
    "key2": "val2"
  },
  "account_sid": "account_sid2",
  "workspace_sid": "workspace_sid6",
  "url": "url0",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

