Override a cooldown tag of the entity. Note that this is can only target global cooldown tags. When a mob loses a target, these are reset.

Do not use cooldowns for precise conditions, a lagging server might offset the expected ticks and archived ticks - cooldown is mostly there to give players an **approximate wait time**.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | string | | cooldown | yes | no |
| duration | ticks | duration of the cooldown | 20 | no | yes |
| channel | string | cooldown channel we are overriding | | yes | no |