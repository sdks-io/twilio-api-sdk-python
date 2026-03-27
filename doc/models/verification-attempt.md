
# Verification Attempt

*This model accepts additional fields of type Any.*

## Structure

`VerificationAttempt`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sid` | `str` | Optional | The SID that uniquely identifies the verification attempt resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^VL[0-9a-fA-F]{32}$` |
| `account_sid` | `str` | Optional | The SID of the [Account](https://www.twilio.com/docs/iam/api/account) that created the Verification resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^AC[0-9a-fA-F]{32}$` |
| `service_sid` | `str` | Optional | The SID of the [Service](https://www.twilio.com/docs/verify/api/service) used to generate the attempt.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^VA[0-9a-fA-F]{32}$` |
| `verification_sid` | `str` | Optional | The SID of the [Verification](https://www.twilio.com/docs/verify/api/verification) that generated the attempt.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^VE[0-9a-fA-F]{32}$` |
| `date_created` | `datetime` | Optional | The date that this Attempt was created, given in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format. |
| `date_updated` | `datetime` | Optional | The date that this Attempt was updated, given in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format. |
| `conversion_status` | [`VerificationAttemptEnumConversionStatus`](../../doc/models/verification-attempt-enum-conversion-status.md) | Optional | A string specifying the conversion status of the verification. A conversion happens when the user is able to provide the correct code. Possible values are `CONVERTED` and `UNCONVERTED`. |
| `channel` | [`VerificationAttemptEnumChannels`](../../doc/models/verification-attempt-enum-channels.md) | Optional | A string specifying the communication channel used for the verification attempt. |
| `price` | `Any` | Optional | An object containing the charge for this verification attempt related to the channel costs and the currency used. The costs related to the succeeded verifications are not included. May not be immediately available. More information on pricing is available [here](https://www.twilio.com/en-us/verify/pricing). |
| `channel_data` | `Any` | Optional | An object containing the channel specific information for an attempt. |
| `url` | `str` | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "sid": "sid4",
  "account_sid": "account_sid8",
  "service_sid": "service_sid0",
  "verification_sid": "verification_sid2",
  "date_created": "2016-03-13T12:52:32.123Z",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

