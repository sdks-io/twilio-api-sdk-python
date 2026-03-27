# Verify V2 Service

```python
verify_v_2_service_api = client.verify_v_2_service
```

## Class Name

`VerifyV2ServiceApi`


# Create Service

Create a new Verification Service.

```python
def create_service(self,
                  friendly_name,
                  code_length=None,
                  lookup_enabled=None,
                  skip_sms_to_landlines=None,
                  dtmf_input_required=None,
                  tts_name=None,
                  psd_2_enabled=None,
                  do_not_share_warning_enabled=None,
                  custom_code_enabled=None,
                  push_include_date=None,
                  push_apn_credential_sid=None,
                  push_fcm_credential_sid=None,
                  totp_issuer=None,
                  totp_time_step=None,
                  totp_code_length=None,
                  totp_skew=None,
                  default_template_sid=None,
                  whatsapp_msg_service_sid=None,
                  whatsapp_from=None,
                  passkeys_relying_party_id=None,
                  passkeys_relying_party_name=None,
                  passkeys_relying_party_origins=None,
                  passkeys_authenticator_attachment=None,
                  passkeys_discoverable_credentials=None,
                  passkeys_user_verification=None,
                  verify_event_subscription_enabled=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `friendly_name` | `str` | Form, Required | A descriptive string that you create to describe the verification service. It can be up to 32 characters long. **This value should not contain PII.** |
| `code_length` | `int` | Form, Optional | The length of the verification code to generate. Must be an integer value between 4 and 10, inclusive. |
| `lookup_enabled` | `bool` | Form, Optional | Whether to perform a lookup with each verification started and return info about the phone number. |
| `skip_sms_to_landlines` | `bool` | Form, Optional | Whether to skip sending SMS verifications to landlines. Requires `lookup_enabled`. |
| `dtmf_input_required` | `bool` | Form, Optional | Whether to ask the user to press a number before delivering the verify code in a phone call. |
| `tts_name` | `str` | Form, Optional | The name of an alternative text-to-speech service to use in phone calls. Applies only to TTS languages. |
| `psd_2_enabled` | `bool` | Form, Optional | Whether to pass PSD2 transaction parameters when starting a verification. |
| `do_not_share_warning_enabled` | `bool` | Form, Optional | Whether to add a security warning at the end of an SMS verification body. Disabled by default and applies only to SMS. Example SMS body: `Your AppName verification code is: 1234. Don’t share this code with anyone; our employees will never ask for the code` |
| `custom_code_enabled` | `bool` | Form, Optional | Whether to allow sending verifications with a custom code instead of a randomly generated one. |
| `push_include_date` | `bool` | Form, Optional | Optional configuration for the Push factors. If true, include the date in the Challenge's response. Otherwise, the date is omitted from the response. See [Challenge](https://www.twilio.com/docs/verify/api/challenge) resource’s details parameter for more info. Default: false. **Deprecated** do not use this parameter. This timestamp value is the same one as the one found in `date_created`, please use that one instead. |
| `push_apn_credential_sid` | `str` | Form, Optional | Optional configuration for the Push factors. Set the APN Credential for this service. This will allow to send push notifications to iOS devices. See [Credential Resource](https://www.twilio.com/docs/notify/api/credential-resource)<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^CR[0-9a-fA-F]{32}$` |
| `push_fcm_credential_sid` | `str` | Form, Optional | Optional configuration for the Push factors. Set the FCM Credential for this service. This will allow to send push notifications to Android devices. See [Credential Resource](https://www.twilio.com/docs/notify/api/credential-resource)<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^CR[0-9a-fA-F]{32}$` |
| `totp_issuer` | `str` | Form, Optional | Optional configuration for the TOTP factors. Set TOTP Issuer for this service. This will allow to configure the issuer of the TOTP URI. Defaults to the service friendly name if not provided. |
| `totp_time_step` | `int` | Form, Optional | Optional configuration for the TOTP factors. Defines how often, in seconds, are TOTP codes generated. i.e, a new TOTP code is generated every time_step seconds. Must be between 20 and 60 seconds, inclusive. Defaults to 30 seconds |
| `totp_code_length` | `int` | Form, Optional | Optional configuration for the TOTP factors. Number of digits for generated TOTP codes. Must be between 3 and 8, inclusive. Defaults to 6 |
| `totp_skew` | `int` | Form, Optional | Optional configuration for the TOTP factors. The number of time-steps, past and future, that are valid for validation of TOTP codes. Must be between 0 and 2, inclusive. Defaults to 1 |
| `default_template_sid` | `str` | Form, Optional | The default message [template](https://www.twilio.com/docs/verify/api/templates). Will be used for all SMS verifications unless explicitly overriden. SMS channel only.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^HJ[0-9a-fA-F]{32}$` |
| `whatsapp_msg_service_sid` | `str` | Form, Optional | The SID of the Messaging Service containing WhatsApp Sender(s) that Verify will use to send WhatsApp messages to your users.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^MG[0-9a-fA-F]{32}$` |
| `whatsapp_from` | `str` | Form, Optional | The number to use as the WhatsApp Sender that Verify will use to send WhatsApp messages to your users.This WhatsApp Sender must be associated with a Messaging Service SID. |
| `passkeys_relying_party_id` | `str` | Form, Optional | The Relying Party ID for Passkeys. This is the domain of your application, e.g. `example.com`. It is used to identify your application when creating Passkeys. |
| `passkeys_relying_party_name` | `str` | Form, Optional | The Relying Party Name for Passkeys. This is the name of your application, e.g. `Example App`. It is used to identify your application when creating Passkeys. |
| `passkeys_relying_party_origins` | `str` | Form, Optional | The Relying Party Origins for Passkeys. This is the origin of your application, e.g. `login.example.com,www.example.com`. It is used to identify your application when creating Passkeys, it can have multiple origins split by `,`. |
| `passkeys_authenticator_attachment` | `str` | Form, Optional | The Authenticator Attachment for Passkeys. This is the type of authenticator that will be used to create Passkeys. It can be empty or it can have the values `platform`, `cross-platform` or `any`. |
| `passkeys_discoverable_credentials` | `str` | Form, Optional | Indicates whether credentials must be discoverable by the authenticator. It can be empty or it can have the values `required`, `preferred` or `discouraged`. |
| `passkeys_user_verification` | `str` | Form, Optional | The User Verification for Passkeys. This is the type of user verification that will be used to create Passkeys. It can be empty or it can have the values `required`, `preferred` or `discouraged`. |
| `verify_event_subscription_enabled` | `bool` | Form, Optional | Whether to allow verifications from the service to reach the stream-events sinks if configured |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Service2`](../../doc/models/service-2.md).

## Example Usage

```python
friendly_name = 'name'

code_length = 4

lookup_enabled = False

skip_sms_to_landlines = False

dtmf_input_required = False

tts_name = 'name'

psd_2_enabled = False

do_not_share_warning_enabled = False

custom_code_enabled = True

push_apn_credential_sid = 'CRaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

totp_issuer = 'test-issuer'

totp_time_step = 30

totp_code_length = 3

totp_skew = 2

default_template_sid = 'HJaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

verify_event_subscription_enabled = False

result = verify_v_2_service_api.create_service(
    friendly_name,
    code_length=code_length,
    lookup_enabled=lookup_enabled,
    skip_sms_to_landlines=skip_sms_to_landlines,
    dtmf_input_required=dtmf_input_required,
    tts_name=tts_name,
    psd_2_enabled=psd_2_enabled,
    do_not_share_warning_enabled=do_not_share_warning_enabled,
    custom_code_enabled=custom_code_enabled,
    push_apn_credential_sid=push_apn_credential_sid,
    totp_issuer=totp_issuer,
    totp_time_step=totp_time_step,
    totp_code_length=totp_code_length,
    totp_skew=totp_skew,
    default_template_sid=default_template_sid,
    verify_event_subscription_enabled=verify_event_subscription_enabled
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

