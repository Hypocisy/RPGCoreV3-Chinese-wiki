Suspends the target entity activities, meant for mobs. Players are unaffected.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | string | | suspension | yes | no |
| duration | integer | ticks to suspend | 20 | no | yes |
| immunity | percent | 1.0 for total damage immunity | 0.0 | no | yes |
| idle | boolean | the entity AI will temporarily stop working | true | no | no |
| rooted | boolean | the entity will be fixed at its position | true | no | no |
| channel | string | the suspension id, same id can extend. Different Id will fail | false | no | no |