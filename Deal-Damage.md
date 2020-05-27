Triggered if the inflicted damage exceeds the threshold. Damage can either be tracked according to links or per behaviour. If we archive the damage amount the tracker is resetting.

The trigger is fired twice, once before we are running any calculcations (during that time, external sources can modify the damage!) and once after the damage has been calculcated (during that time, we can check if damage exceeds the given threshold!)

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | string | | deal-damage | yes | no |
| require-linked | boolean | damage must be inflicted from a linked skill | false | no | no |
| damage-threshold | decimal | minimum amount of damage inflicted | 0 | no | yes |
| require-finished | boolean | observe the result of the damage | true | no | no |
| wanted-types | type list | damage types (not elements!), must match one of these | any | no | no |
| unwanted-types | type list | damage types (not elements!), none of these may be contained | | no | no |
| use-and | boolean | wanted types will use "AND" instead "OR" | false | no | no |