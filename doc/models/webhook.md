
# Webhook

*This model accepts additional fields of type Any.*

## Structure

`Webhook`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sid` | `str` | Optional | The unique string that we created to identify the Webhook resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^YW[0-9a-fA-F]{32}$` |
| `service_sid` | `str` | Optional | The unique SID identifier of the Service.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^VA[0-9a-fA-F]{32}$` |
| `account_sid` | `str` | Optional | The SID of the [Account](https://www.twilio.com/docs/iam/api/account) that created the Service resource.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^AC[0-9a-fA-F]{32}$` |
| `friendly_name` | `str` | Optional | The string that you assigned to describe the webhook. **This value should not contain PII.** |
| `event_types` | `List[str]` | Optional | The array of events that this Webhook is subscribed to. Possible event types: `*, factor.deleted, factor.created, factor.verified, challenge.approved, challenge.denied` |
| `status` | [`WebhookEnumStatus`](../../doc/models/webhook-enum-status.md) | Optional | The webhook status. Default value is `enabled`. One of: `enabled` or `disabled` |
| `version` | [`WebhookEnumVersion`](../../doc/models/webhook-enum-version.md) | Optional | The webhook version. Default value is `v2` which includes all the latest fields. Version `v1` is legacy and may be removed in the future. |
| `webhook_url` | `str` | Optional | The URL associated with this Webhook. |
| `webhook_method` | [`ConfigurationWebhookMethod`](../../doc/models/configuration-webhook-method.md) | Optional | The method to be used when calling the webhook's URL. |
| `date_created` | `datetime` | Optional | The date and time in GMT when the resource was created specified in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format. |
| `date_updated` | `datetime` | Optional | The date and time in GMT when the resource was last updated specified in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format. |
| `url` | `str` | Optional | The absolute URL of the Webhook resource. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "sid": "sid2",
  "service_sid": "service_sid6",
  "account_sid": "account_sid2",
  "friendly_name": "friendly_name8",
  "event_types": [
    "event_types4",
    "event_types5"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

