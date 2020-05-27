Called upon completing a 'cast' through a tome, this happens AFTER starting to cast a spell.

If among the actions executed by this trigger is a damage mechanic, it will be manually inserted with a "SELF_CAST" damage type. Additionally, all variables will receive a sub type of ":SELF_CAST"

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | / | / | cast | / | / |
| channel | string | the "channel" which uniquely identifies this trigger | / | yes | no |
| casttime | integer | tick time required to cast the skill, zero means instant cast | 20 | no | yes |
| action-locked | boolean | prevents actions being undertaken while in the casting phase | false | no | no |
| max-channelling | integer | maximum duration to channel | / | no | yes |
| channel-cooldown | integer | cooldown after channeling done | 0 | no | yes |
| instruction | instruction | Q (Drop), F (Swap), L (Left), R (Right) - Lead with an R, always 3 characters. | / | yes | no |

You may lead the instruction with an 'S' symbol instead of an 'R', doing so will add a pre-condition for the player to be sneaking. Should a player attempt to cast "SRR", but lack a cast trigger for that, we will instead attempt to cast "RRR" should it exist.

## Channeling with casting

Linked with casting there is the ability to channel, channeling is maintained by holding right click. This is entirely optional to be used.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | / | / | channel | / | / |
| channel | string | channeling id | | yes | no |
| start | boolean | first channeling interval | true | no | no |
| active | boolean | neither first neither last channeling interval | true | no | no |
| finish | boolean | final channeling interval | true | no | no |
| linked | boolean | require channeling skill to be among the linked ones | true | no | no |
| unique | boolean | same id cannot be channelled multiple times | true | no | no | 