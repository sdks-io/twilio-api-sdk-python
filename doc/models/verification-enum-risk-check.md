
# Verification Enum Risk Check

Risk_check overrides Fraud Prevention measures like Fraud Guard, Geo Permissions etc per verification attempt basis, allowing Verify to block traffic considered fraudulent if enabled or bypass active protections if disabled. Can be: `enable`(default) or `disable`. For SMS channel only., Include this parameter with a value of `disable` to skip any kind of risk check on the respective message request.

## Enumeration

`VerificationEnumRiskCheck`

## Fields

| Name |
|  --- |
| `ENABLE` |
| `DISABLE` |

