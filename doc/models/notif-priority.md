
# Notif Priority

The priority of the notification. Can be: `low` or `high` and the default is `high`. A value of `low` optimizes the client app's battery consumption; however, notifications may be delivered with unspecified delay. For FCM and GCM, `low` priority is the same as `Normal` priority. For APNS `low` priority is the same as `5`. A value of `high` sends the notification immediately, and can wake up a sleeping device. For FCM and GCM, `high` is the same as `High` priority. For APNS, `high` is a priority `10`. SMS does not support this property.

## Enumeration

`NotifPriority`

## Fields

| Name |
|  --- |
| `HIGH` |
| `LOW` |

