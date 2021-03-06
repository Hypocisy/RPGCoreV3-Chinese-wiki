You can bind a skill to the [[Skillbar]] and summon a totem using the skill in your place.

If among the actions executed by this trigger is a damage mechanic, it will be manually inserted with a "TOTEM" damage type. Additionally, all variables will receive a sub type of ":TOTEM"

**Warning: It still is the player themselves who cast the skill, just that the original location is the totem location.**

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | / | / | totem | / | / |
| gcd | integer | global cast cooldown, checked before specific cooldown | 0 | no | yes |
| channel | string | uniquely identifying totem channel | | yes | no |
| totem-interval | tick seconds | interval at which the totem runs its actions | 20 | no | yes |
| maximum | integer | maximum of totems summoned concurrently | 1 | no | yes |
| duration | tick seconds | duration of totem | 100 | no | yes |
| warmup | tick seconds | ticks before the totem will start casting its skill | 20 | no | yes |
| trigger-radius | radius of targetting for the totem, wont cast without target. Capped at 16 | 8 | no | yes |
| hostile | boolean | totem will target hostile entities | true | no | no |