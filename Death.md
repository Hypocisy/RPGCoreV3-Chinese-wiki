Called when the entity was killed

The skill variables will also be read from the damage attributes that are involved in this Kill interaction. If you had something which added "ADD 50% TO VARIABLE_DURATION" to the damage attributes of the killing blow, it will affect all variables calculcated by the actions related to this trigger.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | string | | death | yes | no |
| require-linked | boolean | damage must be inflicted from a linked skill | false | no | no |
| elements | string list | elements which we allow (Fire, Cold, ...) | all elements | no | no |
| types | string list | elements types we allow (Attack, Hit, ...) | all types | no | no |
| damage-threshold | decimal | minimum amount of damage inflicted | 0 | no | yes |
| require-critical | boolean | expects the 'CRITICAL' tag | false | no | no |
| overkill-threshold | percentage | damage must be overkill (relative to killed) | 0 | no | yes |
| use-and | boolean | wanted types will use "AND" instead "OR" | false | no | no |
| unwanted-types | type list | damage types (not elements!), none of these may be contained | | no | no |