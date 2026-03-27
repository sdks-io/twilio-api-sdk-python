
# Access Token

*This model accepts additional fields of type Any.*

## Structure

`AccessToken`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sid` | `str` | Optional | A 34 character string that uniquely identifies this Access Token.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^YK[0-9a-fA-F]{32}$` |
| `account_sid` | `str` | Optional | The unique SID identifier of the Account.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^AC[0-9a-fA-F]{32}$` |
| `service_sid` | `str` | Optional | The unique SID identifier of the Verify Service.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^VA[0-9a-fA-F]{32}$` |
| `entity_identity` | `str` | Optional | The unique external identifier for the Entity of the Service. |
| `factor_type` | [`AccessTokenEnumFactorTypes`](../../doc/models/access-token-enum-factor-types.md) | Optional | The Type of the Factor. Currently only `push` is supported. |
| `factor_friendly_name` | `str` | Optional | A human readable description of this factor, up to 64 characters. For a push factor, this can be the device's name. |
| `token` | `str` | Optional | The access token generated for enrollment, this is an encrypted json web token. |
| `url` | `str` | Optional | The URL of this resource. |
| `ttl` | `int` | Optional | How long, in seconds, the access token is valid. Max: 5 minutes<br><br>**Default**: `0` |
| `date_created` | `datetime` | Optional | The date that this access token was created, given in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "ttl": 0,
  "sid": "sid8",
  "account_sid": "account_sid6",
  "service_sid": "service_sid2",
  "entity_identity": "entity_identity0",
  "factor_type": "push",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

