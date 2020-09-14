Broadcasts a signal either to ourself or a target, allowing to execute a certain logic. Level requirement is the highest level the skill of the signal receiver may have. Mobs are unaffected by this requirement. If you fire to self you can read targets via "signalled" from the Signal trigger.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | string | | signal | yes | no |
| channel | string | ID of the channel that is broadcast | / | yes | no |
| tags | string list | A set of tags, only one has to match | / | no | no |
| maximum-level | integer | highest level of a skill that can receive the signal. | -1 | no | yes |
| self | boolean | affects yourself instead of the targets, mostly meant to let you retain the exact targets you want to work with | false | no | no |
| require-linked | boolean | only linked skills can receive the signal | false | no | no | 