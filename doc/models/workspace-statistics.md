
# Workspace Statistics

*This model accepts additional fields of type Any.*

## Structure

`WorkspaceStatistics`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `realtime` | `Any` | Optional | An object that contains the real-time statistics for the Workspace. |
| `cumulative` | `Any` | Optional | An object that contains the cumulative statistics for the Workspace. |
| `account_sid` | `str` | Optional | The SID of the [Account](https://www.twilio.com/docs/iam/api/account) that created the Workspace resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^AC[0-9a-fA-F]{32}$` |
| `workspace_sid` | `str` | Optional | The SID of the Workspace.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `url` | `str` | Optional | The absolute URL of the Workspace statistics resource. |
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
  "account_sid": "account_sid0",
  "workspace_sid": "workspace_sid8",
  "url": "url8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

