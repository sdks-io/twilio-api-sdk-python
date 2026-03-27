
# Configuration Webhook Method

The HTTP method to be used when sending a webhook request., The HTTP method we should use to call `conference_recording_status_callback`. Can be: `GET` or `POST` and defaults to `POST`., The HTTP method we should use to call `conference_status_callback`. Can be: `GET` or `POST` and defaults to `POST`., The HTTP method we should use when we call `recording_status_callback`. Can be: `GET` or `POST` and defaults to `POST`., The HTTP method we should use to call `status_callback`. Can be: `POST` or `GET` and the default is `POST`., The HTTP method we should use to call `wait_url`. Can be `GET` or `POST` and the default is `POST`. When using a static audio file, this should be `GET` so that we can cache the file., The method to be used when calling the webhook's URL.

## Enumeration

`ConfigurationWebhookMethod`

## Fields

| Name |
|  --- |
| `GET` |
| `POST` |

