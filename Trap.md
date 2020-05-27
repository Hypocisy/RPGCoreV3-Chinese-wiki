Called upon a trap being triggered, note that if you have multiple traps triggered it will set them off in sequence. The interval is fixed at 0.1s per trap triggered.

Check [[OffhandModule: Traps]] and [[ItemModule: Offhand]]

If among the actions executed by this trigger is a damage mechanic, it will be manually inserted with a "TRAP" damage type. Additionally, all variables will receive a sub type of ":TRAP"

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | / | / | trap | / | / |
| hostile | boolean | triggers when a hostile entity enters range | true | no | no |
| duration | tick seconds | duration that the trap remains before triggering by itself | 200 | yes | yes |
| trigger-radius | integer | the radius within which the proximity check is active | 3 | yes | yes |
| trap-total | integer | the total of concurrent traps that can be placed | 3 | yes | yes |
| place-cooldown | tick seconds | placing cooldown applied once the trap was marked to trigger | / | no | no |