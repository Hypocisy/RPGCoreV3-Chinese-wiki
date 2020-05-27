Summons a minion for the caster, should they be able to still summon one. Note that the limitation of summoning types **and** the limitation of this mechanic is applied.

You may want to check [[EntityModule: Creatures]] for further details on creatures, the summoned creature will be inheriting the hostile and friendly checks of the parent.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | / | / | minion | / | / |
| can-recurse | boolean | minion can summon minion | false | no | no |
| setup | entity id or entity configuration | | / | yes | no |
| level | integer | levels summed atop summoned level | 0 | no | yes |
| limit | integer | limit of concurrently summon minions of this mechanic | 2 | no | yes |
| duration | integer | ticks of minion activity, careful about hacking around with high values | 200 | no | yes |