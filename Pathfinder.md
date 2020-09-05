Attempts to path towards the target location, _this will only path the entity who used the mechanic!_ This is NOT meant to be used absolutely, it is a best effort case. The pathing may fail or be interrupted.

# Mechanic

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | string | | pathfinder | yes | no |
| id | string | while pathing (can be interrupted!) notifies the trigger | false | no | no |

# Trigger

While we are maintaining the pathing the trigger will notified constantly, however the pathfinder may be interrupted for any reason and cease the calls to it earlier then expected.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | string | | pathfinder | yes | no |
| id | string | the id of the mechanic we expect | false | no | no |