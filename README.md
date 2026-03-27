
# Getting Started with Twilio APIs

## Install the Package

The package is compatible with Python versions `3.7+`.
Install the package from PyPi using the following pip command:

```bash
pip install twilio-api-sdk==1.0.0
```

You can also view the package at:
https://pypi.python.org/pypi/twilio-api-sdk/1.0.0

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| environment | [`Environment`](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/README.md#environments) | The API environment. <br> **Default: `Environment.PRODUCTION`** |
| http_client_instance | `Union[Session, HttpClientProvider]` | The Http Client passed from the sdk user for making requests |
| override_http_client_configuration | `bool` | The value which determines to override properties of the passed Http Client from the sdk user |
| http_call_back | `HttpCallBack` | The callback value that is invoked before and after an HTTP call is made to an endpoint |
| timeout | `float` | The value to use for connection timeout. <br> **Default: 30** |
| max_retries | `int` | The number of times to retry an endpoint call if it fails. <br> **Default: 0** |
| backoff_factor | `float` | A backoff factor to apply between attempts after the second try. <br> **Default: 2** |
| retry_statuses | `Array of int` | The http statuses on which retry is to be done. <br> **Default: [408, 413, 429, 500, 502, 503, 504, 521, 522, 524]** |
| retry_methods | `Array of string` | The http methods on which retry is to be done. <br> **Default: ["GET", "PUT"]** |
| proxy_settings | [`ProxySettings`](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/proxy-settings.md) | Optional proxy configuration to route HTTP requests through a proxy server. |
| logging_configuration | [`LoggingConfiguration`](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/logging-configuration.md) | The SDK logging configuration for API calls |
| basic_auth_credentials | [`BasicAuthCredentials`](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/auth/basic-authentication.md) | The credential object for Basic Authentication |

The API client can be initialized as follows:

### Code-Based Client Initialization

```python
import logging

from twilioapis.configuration import Environment
from twilioapis.http.auth.basic_auth import BasicAuthCredentials
from twilioapis.logging.configuration.api_logging_configuration import LoggingConfiguration
from twilioapis.logging.configuration.api_logging_configuration import RequestLoggingConfiguration
from twilioapis.logging.configuration.api_logging_configuration import ResponseLoggingConfiguration
from twilioapis.twilioapis_client import TwilioapisClient

client = TwilioapisClient(
    basic_auth_credentials=BasicAuthCredentials(
        username='BasicAuthUserName',
        password='BasicAuthPassword'
    ),
    environment=Environment.PRODUCTION,
    logging_configuration=LoggingConfiguration(
        log_level=logging.INFO,
        request_logging_config=RequestLoggingConfiguration(
            log_body=True
        ),
        response_logging_config=ResponseLoggingConfiguration(
            log_headers=True
        )
    )
)
```

### Environment-Based Client Initialization

```python
from twilioapis.twilioapis_client import TwilioapisClient

# Specify the path to your .env file if it’s located outside the project’s root directory.
client = TwilioapisClient.from_environment(dotenv_path='/path/to/.env')
```

See the [Environment-Based Client Initialization](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/environment-based-client-initialization.md) section for details.

## Environments

The SDK can be configured to use a different environment for making API calls. Available environments are:

### Fields

| Name | Description |
|  --- | --- |
| PRODUCTION | **Default** |

## Authorization

This API uses the following authentication schemes.

* [`accountSid_authToken (Basic Authentication)`](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/auth/basic-authentication.md)

## List of APIs

* [Accounts V1 Auth Token Promotion](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/accounts-v1-auth-token-promotion.md)
* [Accounts V1 Aws](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/accounts-v1-aws.md)
* [Accounts V1 Bulk Consents](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/accounts-v1-bulk-consents.md)
* [Accounts V1 Bulk Contacts](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/accounts-v1-bulk-contacts.md)
* [Accounts V1 Messaging Geopermissions](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/accounts-v1-messaging-geopermissions.md)
* [Accounts V1 Public Key](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/accounts-v1-public-key.md)
* [Accounts V1 Safelist](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/accounts-v1-safelist.md)
* [Accounts V1 Secondary Auth Token](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/accounts-v1-secondary-auth-token.md)
* [Chat V3 Channel](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/chat-v3-channel.md)
* [Conversations V1 Address Configuration](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/conversations-v1-address-configuration.md)
* [Conversations V1 Binding](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/conversations-v1-binding.md)
* [Conversations V1 Configuration](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/conversations-v1-configuration.md)
* [Conversations V1 Conversation](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/conversations-v1-conversation.md)
* [Conversations V1 Conversation with Participants](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/conversations-v1-conversation-with-participants.md)
* [Conversations V1 Credential](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/conversations-v1-credential.md)
* [Conversations V1 Delivery Receipt](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/conversations-v1-delivery-receipt.md)
* [Conversations V1 Message](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/conversations-v1-message.md)
* [Conversations V1 Notification](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/conversations-v1-notification.md)
* [Conversations V1 Participant](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/conversations-v1-participant.md)
* [Conversations V1 Participant Conversation](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/conversations-v1-participant-conversation.md)
* [Conversations V1 Role](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/conversations-v1-role.md)
* [Conversations V1 Service](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/conversations-v1-service.md)
* [Conversations V1 User](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/conversations-v1-user.md)
* [Conversations V1 User Conversation](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/conversations-v1-user-conversation.md)
* [Conversations V1 Webhook](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/conversations-v1-webhook.md)
* [Notify V1 Binding](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/notify-v1-binding.md)
* [Notify V1 Credential](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/notify-v1-credential.md)
* [Notify V1 Notification](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/notify-v1-notification.md)
* [Notify V1 Service](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/notify-v1-service.md)
* [Taskrouter V1 Activity](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/taskrouter-v1-activity.md)
* [Taskrouter V1 Event](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/taskrouter-v1-event.md)
* [Taskrouter V1 Task](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/taskrouter-v1-task.md)
* [Taskrouter V1 Task Channel](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/taskrouter-v1-task-channel.md)
* [Taskrouter V1 Task Queue](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/taskrouter-v1-task-queue.md)
* [Taskrouter V1 Task Queue Bulk Real Time Statistics](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/taskrouter-v1-task-queue-bulk-real-time-statistics.md)
* [Taskrouter V1 Task Queue Cumulative Statistics](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/taskrouter-v1-task-queue-cumulative-statistics.md)
* [Taskrouter V1 Task Queue Real Time Statistics](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/taskrouter-v1-task-queue-real-time-statistics.md)
* [Taskrouter V1 Task Queue Statistics](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/taskrouter-v1-task-queue-statistics.md)
* [Taskrouter V1 Task Queues Statistics](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/taskrouter-v1-task-queues-statistics.md)
* [Taskrouter V1 Task Reservation](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/taskrouter-v1-task-reservation.md)
* [Taskrouter V1 Worker](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/taskrouter-v1-worker.md)
* [Taskrouter V1 Worker Channel](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/taskrouter-v1-worker-channel.md)
* [Taskrouter V1 Worker Reservation](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/taskrouter-v1-worker-reservation.md)
* [Taskrouter V1 Worker Statistics](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/taskrouter-v1-worker-statistics.md)
* [Taskrouter V1 Workers Cumulative Statistics](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/taskrouter-v1-workers-cumulative-statistics.md)
* [Taskrouter V1 Workers Real Time Statistics](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/taskrouter-v1-workers-real-time-statistics.md)
* [Taskrouter V1 Workers Statistics](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/taskrouter-v1-workers-statistics.md)
* [Taskrouter V1 Workflow](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/taskrouter-v1-workflow.md)
* [Taskrouter V1 Workflow Cumulative Statistics](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/taskrouter-v1-workflow-cumulative-statistics.md)
* [Taskrouter V1 Workflow Real Time Statistics](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/taskrouter-v1-workflow-real-time-statistics.md)
* [Taskrouter V1 Workflow Statistics](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/taskrouter-v1-workflow-statistics.md)
* [Taskrouter V1 Workspace](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/taskrouter-v1-workspace.md)
* [Taskrouter V1 Workspace Cumulative Statistics](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/taskrouter-v1-workspace-cumulative-statistics.md)
* [Taskrouter V1 Workspace Real Time Statistics](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/taskrouter-v1-workspace-real-time-statistics.md)
* [Taskrouter V1 Workspace Statistics](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/taskrouter-v1-workspace-statistics.md)
* [Verify V2 Service](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/verify-v2-service.md)
* [Verify V2 Verification](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/verify-v2-verification.md)
* [Verify V2 Verification Check](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/controllers/verify-v2-verification-check.md)

## SDK Infrastructure

### Configuration

* [ProxySettings](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/proxy-settings.md)
* [Environment-Based Client Initialization](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/environment-based-client-initialization.md)
* [AbstractLogger](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/abstract-logger.md)
* [LoggingConfiguration](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/logging-configuration.md)
* [RequestLoggingConfiguration](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/request-logging-configuration.md)
* [ResponseLoggingConfiguration](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/response-logging-configuration.md)

### HTTP

* [HttpResponse](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/http-response.md)
* [HttpRequest](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/http-request.md)

### Utilities

* [ApiResponse](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/api-response.md)
* [ApiHelper](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/api-helper.md)
* [HttpDateTime](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/http-date-time.md)
* [RFC3339DateTime](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/rfc3339-date-time.md)
* [UnixDateTime](https://www.github.com/sdks-io/twilio-api-sdk-python/tree/1.0.0/doc/unix-date-time.md)

