
# Verification Template

*This model accepts additional fields of type Any.*

## Structure

`VerificationTemplate`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sid` | `str` | Optional | A 34 character string that uniquely identifies a Verification Template.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^HJ[0-9a-fA-F]{32}$` |
| `account_sid` | `str` | Optional | The unique SID identifier of the Account.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^AC[0-9a-fA-F]{32}$` |
| `friendly_name` | `str` | Optional | A descriptive string that you create to describe a Template. It can be up to 32 characters long. |
| `channels` | `List[str]` | Optional | A list of channels that support the Template. Can include: sms, voice. |
| `translations` | `Any` | Optional | An object that contains the different translations of the template. Every translation is identified by the language short name and contains its respective information as the approval status, text and created/modified date. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "sid": "sid8",
  "account_sid": "account_sid2",
  "friendly_name": "friendly_name2",
  "channels": [
    "channels1",
    "channels0"
  ],
  "translations": {
    "key1": "val1",
    "key2": "val2"
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

