Verifies the state of a flag, should the cycle not exist we will attempt generating it.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | / | / | flag | / | / |
| id | string | id of the flag to check | / | yes | no |
| type | flag class | IDLE_BOOLEAN and TEMP_BOOLEAN are supported inherently | TEMP_BOOLEAN | no | no |
| target | flag value | Value of the flag that we want | / | yes | no |

## Flag Type: TEMP_BOOLEAN

When it changes to true, it will return to false after a while

## Flag Type: IDLE_BOOLEAN

When it changes the value, it will retain it until manually updated