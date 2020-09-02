You can bind a skill to the [[Skillbar]] and "self cast" it.

If among the actions executed by this trigger is a damage mechanic, it will be manually inserted with a "SELF_CAST" damage type. Additionally, all variables will receive a sub type of ":SELF_CAST"

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | / | / | cast | / | / |
| casttime | integer | duration to use this ability | 20 | no | yes |
| channel-cooldown | integer | cooldown after the skill finished | / | no | yes |
| max-channelling | integer | maximum duration to channel | / | no | yes |
| action-locked | boolean | prevent actions while casting | false | no | no | 
| channeling-id | string | id during channeling | / | no | no | 

## Channeling with casting

Only the channeling trigger from the same skill is fired, the id has to be the `channeling-id` of the cast trigger. You cannot channel from totems or traps, it is a mechanic specific to self casting.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | / | / | channeling | / | / |
| channel | string | channeling id | | yes | no |
| start | boolean | first channeling interval | true | no | no |
| active | boolean | neither first neither last channeling interval | true | no | no |
| finish | boolean | final channeling interval | true | no | no |
| linked | boolean | require channeling skill to be among the linked ones | true | no | no |
| unique | boolean | same id cannot be channelled multiple times | true | no | no | 