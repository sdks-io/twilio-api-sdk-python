
# Configuration Address

*This model accepts additional fields of type Any.*

## Structure

`ConfigurationAddress`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sid` | `str` | Optional | A 34 character string that uniquely identifies this resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IG[0-9a-fA-F]{32}$` |
| `account_sid` | `str` | Optional | The unique ID of the [Account](https://www.twilio.com/docs/iam/api/account) the address belongs to<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^AC[0-9a-fA-F]{32}$` |
| `mtype` | `str` | Optional | Type of Address, value can be `whatsapp` or `sms`. |
| `address` | `str` | Optional | The unique address to be configured. The address can be a whatsapp address or phone number |
| `friendly_name` | `str` | Optional | The human-readable name of this configuration, limited to 256 characters. Optional. |
| `auto_creation` | `Any` | Optional | Auto Creation configuration for the address. |
| `date_created` | `datetime` | Optional | The date that this resource was created. |
| `date_updated` | `datetime` | Optional | The date that this resource was last updated. |
| `url` | `str` | Optional | An absolute API resource URL for this address configuration. |
| `address_country` | `str` | Optional | An ISO 3166-1 alpha-2n country code which the address belongs to. This is currently only applicable to short code addresses. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "sid": "sid4",
  "account_sid": "account_sid8",
  "type": "type8",
  "address": "address8",
  "friendly_name": "friendly_name8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

