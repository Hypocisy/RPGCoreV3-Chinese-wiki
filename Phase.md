An entity may have multiple phases, [[Skills: Triggers]] can filter for phases in their notation.

# Mechanic

Update the state of a given phase for the target entity.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | string | | phase | yes | no |
| id | string | id of the phase to update | DEFAULT | no | no |
| value | string | value to update phase to | DEFAULT | no | no |

# Condition

Verify the state of a given phase for the target entity

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | string | | phase | yes | no |
| id | string | id of the phase to check | DEFAULT | no | no |
| value | string | value that we require | DEFAULT | no | no |
