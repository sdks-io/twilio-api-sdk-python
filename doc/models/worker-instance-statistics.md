
# Worker Instance Statistics

*This model accepts additional fields of type Any.*

## Structure

`WorkerInstanceStatistics`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `account_sid` | `str` | Optional | The SID of the [Account](https://www.twilio.com/docs/iam/api/account) that created the Worker resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^AC[0-9a-fA-F]{32}$` |
| `cumulative` | `Any` | Optional | An object that contains the cumulative statistics for the Worker. |
| `worker_sid` | `str` | Optional | The SID of the Worker that contains the WorkerChannel.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WK[0-9a-fA-F]{32}$` |
| `workspace_sid` | `str` | Optional | The SID of the Workspace that contains the WorkerChannel.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `url` | `str` | Optional | The absolute URL of the WorkerChannel statistics resource. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "account_sid": "account_sid8",
  "cumulative": {
    "key1": "val1",
    "key2": "val2"
  },
  "worker_sid": "worker_sid0",
  "workspace_sid": "workspace_sid0",
  "url": "url6",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

