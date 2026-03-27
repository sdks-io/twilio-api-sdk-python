
# V2 Services Verifications 429 Error Exception

*This model accepts additional fields of type Any.*

## Structure

`V2ServicesVerifications429ErrorException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `code` | `int` | Optional | Twilio-specific error code |
| `message` | `str` | Optional | Error message |
| `more_info` | `str` | Optional | Link to Error Code References |
| `status` | `int` | Optional | HTTP response status code |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "code": 0,
  "message": "message0",
  "more_info": "more_info2",
  "status": 178,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

