Adds an attachment to the entity, do **not** attempt to give the targets primary or secondary attachments - no guarantee is made about the results of such an action.

When a cluster is defined, the maximum attachments is based on the limit of the one who is using the mechanic rather then the target of it. The extra limit is adding atop the said limit, and is not affected by the modifiers of it.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | string | | attachment | yes | no |
| stacks | integer | maximum stacking, see [[SkillModule: Variables]] | 1 | no | yes |
| duration | ticks | maximum duration, see [[SkillModule: Variables]] | 100 | no | yes |
| individual | boolean | how to count stack duration | false | no | no |
| as-proxy | boolean | Sets the origin to the parent. | false | no | no |
| extra-limit | integer | adds to the limit of a cluster | 0 | no | yes |
| ignore-limit | boolean | bypass the limit of a cluster | false | no | no |
| behaviours | string | keying of behaviours to add | | yes | no |
| inherit-data | boolean | inherit preceding event data | false | no | no |