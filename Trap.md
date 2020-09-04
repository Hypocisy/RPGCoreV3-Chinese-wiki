You can bind a skill to the [[Skillbar]] and place a trap that can be triggered. If you have multiple traps triggered it will set them off in sequence. The interval is fixed at 0.1s per trap triggered.

If among the actions executed by this trigger is a damage mechanic, it will be manually inserted with a "TRAP" damage type. Additionally, all variables will receive a sub type of ":TRAP"

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | / | / | trap | / | / |
| gcd | integer | global cast cooldown, checked before specific cooldown | 0 | no | yes |
| hostile | boolean | triggers when a hostile entity enters range | true | no | no |
| duration | tick seconds | duration that the trap remains before triggering by itself | 200 | yes | yes |
| trigger-radius | integer | the radius within which the proximity check is active | 3 | yes | yes |
| trap-total | integer | the total of concurrent traps that can be placed | 3 | yes | yes |
| place-cooldown | tick seconds | placing cooldown applied once the trap was marked to trigger | / | no | no |