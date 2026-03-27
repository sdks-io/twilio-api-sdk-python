
# Workflow

*This model accepts additional fields of type Any.*

## Structure

`Workflow`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `account_sid` | `str` | Optional | The SID of the [Account](https://www.twilio.com/docs/iam/api/account) that created the Workflow resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^AC[0-9a-fA-F]{32}$` |
| `assignment_callback_url` | `str` | Optional | The URL that we call when a task managed by the Workflow is assigned to a Worker. See Assignment Callback URL for more information. |
| `configuration` | `str` | Optional | A JSON string that contains the Workflow's configuration. See [Configuring Workflows](https://www.twilio.com/docs/taskrouter/workflow-configuration) for more information. |
| `date_created` | `datetime` | Optional | The date and time in GMT when the resource was created specified in [RFC 2822](https://www.ietf.org/rfc/rfc2822.txt) format. |
| `date_updated` | `datetime` | Optional | The date and time in GMT when the resource was last updated specified in [RFC 2822](https://www.ietf.org/rfc/rfc2822.txt) format. |
| `document_content_type` | `str` | Optional | The MIME type of the document. |
| `fallback_assignment_callback_url` | `str` | Optional | The URL that we call when a call to the `assignment_callback_url` fails. |
| `friendly_name` | `str` | Optional | The string that you assigned to describe the Workflow resource. For example, `Customer Support` or `2014 Election Campaign`. |
| `sid` | `str` | Optional | The unique string that we created to identify the Workflow resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WW[0-9a-fA-F]{32}$` |
| `task_reservation_timeout` | `int` | Optional | How long TaskRouter will wait for a confirmation response from your application after it assigns a Task to a Worker. Can be up to `86,400` (24 hours) and the default is `120`.<br><br>**Default**: `0` |
| `workspace_sid` | `str` | Optional | The SID of the Workspace that contains the Workflow.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^WS[0-9a-fA-F]{32}$` |
| `url` | `str` | Optional | The absolute URL of the Workflow resource. |
| `links` | `Any` | Optional | The URLs of related resources. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "task_reservation_timeout": 0,
  "account_sid": "account_sid8",
  "assignment_callback_url": "assignment_callback_url0",
  "configuration": "configuration4",
  "date_created": "2016-03-13T12:52:32.123Z",
  "date_updated": "2016-03-13T12:52:32.123Z",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

