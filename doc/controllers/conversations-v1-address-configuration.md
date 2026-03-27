# Conversations V1 Address Configuration

```python
conversations_v_1_address_configuration_api = client.conversations_v_1_address_configuration
```

## Class Name

`ConversationsV1AddressConfigurationApi`

## Methods

* [List Configuration Address](../../doc/controllers/conversations-v1-address-configuration.md#list-configuration-address)
* [Create Configuration Address](../../doc/controllers/conversations-v1-address-configuration.md#create-configuration-address)
* [Fetch Configuration Address](../../doc/controllers/conversations-v1-address-configuration.md#fetch-configuration-address)
* [Update Configuration Address](../../doc/controllers/conversations-v1-address-configuration.md#update-configuration-address)
* [Delete Configuration Address](../../doc/controllers/conversations-v1-address-configuration.md#delete-configuration-address)


# List Configuration Address

Retrieve a list of address configurations for an account

```python
def list_configuration_address(self,
                              mtype=None,
                              page_size=None,
                              page=None,
                              page_token=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `mtype` | `str` | Query, Optional | Filter the address configurations by its type. This value can be one of: `whatsapp`, `sms`. |
| `page_size` | `int` | Query, Optional | How many resources to return in each list page. The default is 50, and the maximum is 50.<br><br>**Constraints**: `>= 1`, `<= 50` |
| `page` | `int` | Query, Optional | The page index. This value is simply for client state.<br><br>**Constraints**: `>= 0` |
| `page_token` | `str` | Query, Optional | The page token. This is provided by the API. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ListConfigurationAddressResponse`](../../doc/models/list-configuration-address-response.md).

## Example Usage

```python
mtype = 'sms'

result = conversations_v_1_address_configuration_api.list_configuration_address(
    mtype=mtype
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Create Configuration Address

Create a new address configuration

```python
def create_configuration_address(self,
                                mtype,
                                address,
                                friendly_name=None,
                                auto_creation_enabled=None,
                                auto_creation_type=None,
                                auto_creation_conversation_service_sid=None,
                                auto_creation_webhook_url=None,
                                auto_creation_webhook_method=None,
                                auto_creation_webhook_filters=None,
                                auto_creation_studio_flow_sid=None,
                                auto_creation_studio_retry_count=None,
                                address_country=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `mtype` | [`ConfigurationAddressType`](../../doc/models/configuration-address-type.md) | Form, Required | Type of Address, value can be `whatsapp` or `sms`. |
| `address` | `str` | Form, Required | The unique address to be configured. The address can be a whatsapp address or phone number |
| `friendly_name` | `str` | Form, Optional | The human-readable name of this configuration, limited to 256 characters. Optional. |
| `auto_creation_enabled` | `bool` | Form, Optional | Enable/Disable auto-creating conversations for messages to this address |
| `auto_creation_type` | [`ConfigurationAddressAutoCreationType`](../../doc/models/configuration-address-auto-creation-type.md) | Form, Optional | - |
| `auto_creation_conversation_service_sid` | `str` | Form, Optional | Conversation Service for the auto-created conversation. If not set, the conversation is created in the default service.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `auto_creation_webhook_url` | `str` | Form, Optional | For type `webhook`, the url for the webhook request. |
| `auto_creation_webhook_method` | [`ConfigurationAddressMethod`](../../doc/models/configuration-address-method.md) | Form, Optional | - |
| `auto_creation_webhook_filters` | `List[str]` | Form, Optional | The list of events, firing webhook event for this Conversation. Values can be any of the following: `onMessageAdded`, `onMessageUpdated`, `onMessageRemoved`, `onConversationUpdated`, `onConversationStateUpdated`, `onConversationRemoved`, `onParticipantAdded`, `onParticipantUpdated`, `onParticipantRemoved`, `onDeliveryUpdated` |
| `auto_creation_studio_flow_sid` | `str` | Form, Optional | For type `studio`, the studio flow SID where the webhook should be sent to.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^FW[0-9a-fA-F]{32}$` |
| `auto_creation_studio_retry_count` | `int` | Form, Optional | For type `studio`, number of times to retry the webhook request |
| `address_country` | `str` | Form, Optional | An ISO 3166-1 alpha-2n country code which the address belongs to. This is currently only applicable to short code addresses. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConfigurationAddress`](../../doc/models/configuration-address.md).

## Example Usage

```python
mtype = ConfigurationAddressType.SMS

address = '+37256123457'

friendly_name = 'My Test Configuration'

auto_creation_enabled = True

auto_creation_type = ConfigurationAddressAutoCreationType.WEBHOOK

auto_creation_conversation_service_sid = 'ISaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

auto_creation_webhook_url = 'https://example.com'

auto_creation_webhook_method = ConfigurationAddressMethod.POST

auto_creation_webhook_filters = [
    'onParticipantAdded',
    'onMessageAdded'
]

address_country = 'CA'

result = conversations_v_1_address_configuration_api.create_configuration_address(
    mtype,
    address,
    friendly_name=friendly_name,
    auto_creation_enabled=auto_creation_enabled,
    auto_creation_type=auto_creation_type,
    auto_creation_conversation_service_sid=auto_creation_conversation_service_sid,
    auto_creation_webhook_url=auto_creation_webhook_url,
    auto_creation_webhook_method=auto_creation_webhook_method,
    auto_creation_webhook_filters=auto_creation_webhook_filters,
    address_country=address_country
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Fetch Configuration Address

Fetch an address configuration

```python
def fetch_configuration_address(self,
                               sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sid` | `str` | Template, Required | The SID of the Address Configuration resource. This value can be either the `sid` or the `address` of the configuration |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConfigurationAddress`](../../doc/models/configuration-address.md).

## Example Usage

```python
sid = 'Sid8'

result = conversations_v_1_address_configuration_api.fetch_configuration_address(sid)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Update Configuration Address

Update an existing address configuration

```python
def update_configuration_address(self,
                                sid,
                                friendly_name=None,
                                auto_creation_enabled=None,
                                auto_creation_type=None,
                                auto_creation_conversation_service_sid=None,
                                auto_creation_webhook_url=None,
                                auto_creation_webhook_method=None,
                                auto_creation_webhook_filters=None,
                                auto_creation_studio_flow_sid=None,
                                auto_creation_studio_retry_count=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sid` | `str` | Template, Required | The SID of the Address Configuration resource. This value can be either the `sid` or the `address` of the configuration |
| `friendly_name` | `str` | Form, Optional | The human-readable name of this configuration, limited to 256 characters. Optional. |
| `auto_creation_enabled` | `bool` | Form, Optional | Enable/Disable auto-creating conversations for messages to this address |
| `auto_creation_type` | [`ConfigurationAddressAutoCreationType`](../../doc/models/configuration-address-auto-creation-type.md) | Form, Optional | - |
| `auto_creation_conversation_service_sid` | `str` | Form, Optional | Conversation Service for the auto-created conversation. If not set, the conversation is created in the default service.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^IS[0-9a-fA-F]{32}$` |
| `auto_creation_webhook_url` | `str` | Form, Optional | For type `webhook`, the url for the webhook request. |
| `auto_creation_webhook_method` | [`ConfigurationAddressMethod`](../../doc/models/configuration-address-method.md) | Form, Optional | - |
| `auto_creation_webhook_filters` | `List[str]` | Form, Optional | The list of events, firing webhook event for this Conversation. Values can be any of the following: `onMessageAdded`, `onMessageUpdated`, `onMessageRemoved`, `onConversationUpdated`, `onConversationStateUpdated`, `onConversationRemoved`, `onParticipantAdded`, `onParticipantUpdated`, `onParticipantRemoved`, `onDeliveryUpdated` |
| `auto_creation_studio_flow_sid` | `str` | Form, Optional | For type `studio`, the studio flow SID where the webhook should be sent to.<br><br>**Constraints**: *Minimum Length*: `34`, *Maximum Length*: `34`, *Pattern*: `^FW[0-9a-fA-F]{32}$` |
| `auto_creation_studio_retry_count` | `int` | Form, Optional | For type `studio`, number of times to retry the webhook request |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConfigurationAddress`](../../doc/models/configuration-address.md).

## Example Usage

```python
sid = 'Sid8'

friendly_name = 'My Test Configuration Updated'

auto_creation_enabled = False

auto_creation_type = ConfigurationAddressAutoCreationType.STUDIO

auto_creation_studio_flow_sid = 'FWaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'

auto_creation_studio_retry_count = 3

result = conversations_v_1_address_configuration_api.update_configuration_address(
    sid,
    friendly_name=friendly_name,
    auto_creation_enabled=auto_creation_enabled,
    auto_creation_type=auto_creation_type,
    auto_creation_studio_flow_sid=auto_creation_studio_flow_sid,
    auto_creation_studio_retry_count=auto_creation_studio_retry_count
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Delete Configuration Address

Remove an existing address configuration

```python
def delete_configuration_address(self,
                                sid)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sid` | `str` | Template, Required | The SID of the Address Configuration resource. This value can be either the `sid` or the `address` of the configuration |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```python
sid = 'Sid8'

result = conversations_v_1_address_configuration_api.delete_configuration_address(sid)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

