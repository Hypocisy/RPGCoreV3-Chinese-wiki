Run multiple targetters and conditions to end up with one specific target.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | / | / | layered | / | / |
| sequence | targetter list | exact ids keyed under **or** string notation | | no | no |

## Additional options added

Every targetter and condition has access to some additional fields to work properly with this "layered" targetter. 

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| blend | Operation | "UNION", "REPLACE", "DIFFERENCE", "ADD" or "REMOVE" | REPLACE | no | no |
| abortable | boolean | abort once no targets are left | false | no | no |