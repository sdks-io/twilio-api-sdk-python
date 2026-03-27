
# Msg Geopermissions

*This model accepts additional fields of type Any.*

## Structure

`MsgGeopermissions`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `permissions` | `Any` | Optional | A list of objects where each object represents the result of processing a messaging Geo Permission. Each object contains the following fields: `country_code`, the country code of the country for which the permission was updated; `type`, the type of the permission i.e. country; `enabled`, true if the permission is enabled else false; `error_code`, an integer where 0 indicates success and any non-zero value represents an error; and `error_messages`, an array of strings describing specific validation errors encountered. If the request is successful, the error_messages array will be empty. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "permissions": {
    "key1": "val1",
    "key2": "val2"
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

