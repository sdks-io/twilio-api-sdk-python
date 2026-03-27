
# Worker

*This model accepts additional fields of type Any.*

## Structure

`Worker`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `account_sid` | `str` | Optional | The SID of the [Account](https://www.twilio.com/docs/iam/api/account) that created the Worker resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^AC[0-9a-fA-F]{32}$` |
| `activity_name` | `str` | Optional | The `friendly_name` of the Worker's current Activity. |
| `activity_sid` | `str` | Optional | The SID of the Worker's current Activity.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WA[0-9a-fA-F]{32}$` |
| `attributes` | `str` | Optional | The JSON string that describes the Worker. For example: `{ "email": "Bob@example.com", "phone": "+5095551234" }`. **Note** If this property has been assigned a value, it will only be displayed in FETCH actions that return a single resource. Otherwise, this property will be null, even if it has a value. This data is passed to the `assignment_callback_url` when TaskRouter assigns a Task to the Worker. |
| `available` | `bool` | Optional | Whether the Worker is available to perform tasks. |
| `date_created` | `datetime` | Optional | The date and time in GMT when the resource was created specified in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format. |
| `date_status_changed` | `datetime` | Optional | The date and time in GMT of the last change to the Worker's activity specified in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format. Used to calculate Workflow statistics. |
| `date_updated` | `datetime` | Optional | The date and time in GMT when the resource was last updated specified in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format. |
| `friendly_name` | `str` | Optional | The string that you assigned to describe the resource. Friendly names are case insensitive, and unique within the TaskRouter Workspace. |
| `sid` | `str` | Optional | The unique string that we created to identify the Worker resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WK[0-9a-fA-F]{32}$` |
| `workspace_sid` | `str` | Optional | The SID of the Workspace that contains the Worker.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `url` | `str` | Optional | The absolute URL of the Worker resource. |
| `links` | `Any` | Optional | The URLs of related resources. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "account_sid": "account_sid4",
  "activity_name": "activity_name6",
  "activity_sid": "activity_sid6",
  "attributes": "attributes2",
  "available": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

