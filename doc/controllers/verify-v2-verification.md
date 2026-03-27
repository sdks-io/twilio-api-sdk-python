# Verify V2 Verification

```python
verify_v_2_verification_api = client.verify_v_2_verification
```

## Class Name

`VerifyV2VerificationApi`


# Create Verification

Create a new Verification using a Service

```python
def create_verification(self,
                       service_sid,
                       to,
                       channel,
                       custom_friendly_name=None,
                       custom_message=None,
                       send_digits=None,
                       locale=None,
                       custom_code=None,
                       amount=None,
                       payee=None,
                       rate_limits=None,
                       channel_configuration=None,
                       app_hash=None,
                       template_sid=None,
                       template_custom_substitutions=None,
                       device_ip=None,
                       enable_sna_client_token=None,
                       risk_check=None,
                       tags=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `service_sid` | `str` | Template, Required | The SID of the verification [Service](https://www.twilio.com/docs/verify/api/service) to create the resource under.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^VA[0-9a-fA-F]{32}$` |
| `to` | `str` | Form, Required | The phone number or [email](https://www.twilio.com/docs/verify/email) to verify. Phone numbers must be in [E.164 format](https://www.twilio.com/docs/glossary/what-e164). |
| `channel` | `str` | Form, Required | The verification method to use. One of: [`email`](https://www.twilio.com/docs/verify/email), `sms`, `whatsapp`, `call`, `sna` or `auto`. |
| `custom_friendly_name` | `str` | Form, Optional | A custom user defined friendly name that overwrites the existing one in the verification message |
| `custom_message` | `str` | Form, Optional | The text of a custom message to use for the verification. |
| `send_digits` | `str` | Form, Optional | The digits to send after a phone call is answered, for example, to dial an extension. For more information, see the Programmable Voice documentation of [sendDigits](https://www.twilio.com/docs/voice/twiml/number#attributes-sendDigits). |
| `locale` | `str` | Form, Optional | Locale will automatically resolve based on phone number country code for SMS, WhatsApp, and call channel verifications. It will fallback to English or the template’s default translation if the selected translation is not available. This parameter will override the automatic locale resolution. [See supported languages and more information here](https://www.twilio.com/docs/verify/supported-languages). |
| `custom_code` | `str` | Form, Optional | A pre-generated code to use for verification. The code can be between 4 and 10 characters, inclusive. |
| `amount` | `str` | Form, Optional | The amount of the associated PSD2 compliant transaction. Requires the PSD2 Service flag enabled. |
| `payee` | `str` | Form, Optional | The payee of the associated PSD2 compliant transaction. Requires the PSD2 Service flag enabled. |
| `rate_limits` | `Any` | Form, Optional | The custom key-value pairs of Programmable Rate Limits. Keys correspond to `unique_name` fields defined when [creating your Rate Limit](https://www.twilio.com/docs/verify/api/service-rate-limits). Associated value pairs represent values in the request that you are rate limiting on. You may include multiple Rate Limit values in each request. |
| `channel_configuration` | `Any` | Form, Optional | [`email`](https://www.twilio.com/docs/verify/email) channel configuration in json format. The fields 'from' and 'from_name' are optional but if included the 'from' field must have a valid email address. |
| `app_hash` | `str` | Form, Optional | Your [App Hash](https://developers.google.com/identity/sms-retriever/verify#computing_your_apps_hash_string) to be appended at the end of your verification SMS body. Applies only to SMS. Example SMS body: `<#> Your AppName verification code is: 1234 He42w354ol9`. |
| `template_sid` | `str` | Form, Optional | The message [template](https://www.twilio.com/docs/verify/api/templates). If provided, will override the default template for the Service. SMS and Voice channels only.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^HJ[0-9a-fA-F]{32}$` |
| `template_custom_substitutions` | `str` | Form, Optional | A stringified JSON object in which the keys are the template's special variables and the values are the variables substitutions. |
| `device_ip` | `str` | Form, Optional | Strongly encouraged if using the auto channel. The IP address of the client's device. If provided, it has to be a valid IPv4 or IPv6 address. |
| `enable_sna_client_token` | `bool` | Form, Optional | An optional Boolean value to indicate the requirement of sna client token in the SNA URL invocation response for added security. This token must match in the Verification Check request to confirm phone number verification. |
| `risk_check` | [`VerificationEnumRiskCheck`](../../doc/models/verification-enum-risk-check.md) | Form, Optional | Risk_check overrides Fraud Prevention measures like Fraud Guard, Geo Permissions etc per verification attempt basis, allowing Verify to block traffic considered fraudulent if enabled or bypass active protections if disabled. Can be: `enable`(default) or `disable`. For SMS channel only. |
| `tags` | `str` | Form, Optional | A string containing a JSON map of key value pairs of tags to be recorded as metadata for the message. The object may contain up to 10 tags. Keys and values can each be up to 128 characters in length. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Verification`](../../doc/models/verification.md).

## Example Usage

```python
service_sid = 'ServiceSid8'

to = '+15017122661'

channel = 'sms'

custom_friendly_name = 'custom_friendly_name'

custom_message = 'custom_message'

send_digits = 'ww1'

locale = 'en'

custom_code = 'custom_code'

amount = '€39.99'

payee = 'Acme Inc.'

rate_limits = jsonpickle.decode('{"my_rate_limit_key":"abc"}')

channel_configuration = jsonpickle.decode('{"from":"foo@bar.com","from_name":"Bar Inc.","substitutions":{"username":"ms. baz"},"template_id":"Dxxxxxxxxxx"}')

app_hash = 'AAAAAAAAAAA'

template_sid = 'HJaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

template_custom_substitutions = '{"AppName": "MyApp", "Contact":"12345689"}'

device_ip = '0.000.00.000'

risk_check = VerificationEnumRiskCheck.ENABLE

tags = '{"tenant_id": "12345"}'

result = verify_v_2_verification_api.create_verification(
    service_sid,
    to,
    channel,
    custom_friendly_name=custom_friendly_name,
    custom_message=custom_message,
    send_digits=send_digits,
    locale=locale,
    custom_code=custom_code,
    amount=amount,
    payee=payee,
    rate_limits=rate_limits,
    channel_configuration=channel_configuration,
    app_hash=app_hash,
    template_sid=template_sid,
    template_custom_substitutions=template_custom_substitutions,
    device_ip=device_ip,
    risk_check=risk_check,
    tags=tags
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 429 | Too Many Requests | [`V2ServicesVerifications429ErrorException`](../../doc/models/v2-services-verifications-429-error-exception.md) |

