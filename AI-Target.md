Updates the target of the mob, this will wipe the previous aggro. The new target has 0 aggro, hence may easily lose the aggro. This is relative to the entity who used the ability. Players are unaffected by this. If we cannot path to the target, the entity will reset to its idle state.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | string | | target | yes | no |