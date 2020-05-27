The modify damage mechanic is meant to be used with the [[Deal Damage]] or [[Take Damage]] trigger. Make sure that you setup it so that is used before the calculcation is finished, otherwise your changes are not applied.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | string | | modify-damage | yes | no |
| from-attacker | boolean | if you access an entity variable, will scale it off the attacker | true | yes | no |
| setup | modifier list | list of the modifiers to the damage | | yes | partial |
| as-baked | boolean | bake the variable to a static value so it wont calculcate again | false | no | no |
| cluster | string | the cluster that will scale this, applied as magnitude | / | no | no |