# Verify V2 Verification Check

```python
verify_v_2_verification_check_api = client.verify_v_2_verification_check
```

## Class Name

`VerifyV2VerificationCheckApi`


# Create Verification Check

challenge a specific Verification Check.

```python
def create_verification_check(self,
                             service_sid,
                             code=None,
                             to=None,
                             verification_sid=None,
                             amount=None,
                             payee=None,
                             sna_client_token=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `service_sid` | `str` | Template, Required | The SID of the verification [Service](https://www.twilio.com/docs/verify/api/service) to create the resource under.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^VA[0-9a-fA-F]{32}$` |
| `code` | `str` | Form, Optional | The 4-10 character string being verified. |
| `to` | `str` | Form, Optional | The phone number or [email](https://www.twilio.com/docs/verify/email) to verify. Either this parameter or the `verification_sid` must be specified. Phone numbers must be in [E.164 format](https://www.twilio.com/docs/glossary/what-e164). |
| `verification_sid` | `str` | Form, Optional | A SID that uniquely identifies the Verification Check. Either this parameter or the `to` phone number/[email](https://www.twilio.com/docs/verify/email) must be specified.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^VE[0-9a-fA-F]{32}$` |
| `amount` | `str` | Form, Optional | The amount of the associated PSD2 compliant transaction. Requires the PSD2 Service flag enabled. |
| `payee` | `str` | Form, Optional | The payee of the associated PSD2 compliant transaction. Requires the PSD2 Service flag enabled. |
| `sna_client_token` | `str` | Form, Optional | A sna client token received in sna url invocation response needs to be passed in Verification Check request and should match to get successful response. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`VerificationCheck`](../../doc/models/verification-check.md).

## Example Usage

```python
service_sid = 'ServiceSid8'

code = '1234'

to = '+15017122661'

verification_sid = 'VEaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

amount = '€39.99'

payee = 'Acme Inc.'

result = verify_v_2_verification_check_api.create_verification_check(
    service_sid,
    code=code,
    to=to,
    verification_sid=verification_sid,
    amount=amount,
    payee=payee
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "sid": "VEaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "service_sid": "VAaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "account_sid": "ACaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
  "to": "+15017122661",
  "channel": "sms",
  "status": "approved",
  "valid": true,
  "amount": null,
  "payee": null,
  "sna_attempts_error_codes": [],
  "date_created": "2015-07-30T20:00:00Z",
  "date_updated": "2015-07-30T20:00:00Z"
}
```

