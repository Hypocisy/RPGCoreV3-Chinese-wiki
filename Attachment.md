Adds an attachment to the entity, do **not** attempt to give the targets primary or secondary attachments - no guarantee is made about the results of such an action.

When a cluster is defined, the maximum attachments is based on the limit of the one who is using the mechanic rather then the target of it. The extra limit is adding atop the said limit, and is not affected by the modifiers of it.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | string | | attachment | yes | no |
| stacks | integer | maximum of stacks which we can have | 1 | no | yes |
| duration | ticks | maximum duration of this attachment | 100 | no | yes |
| individual | boolean | Individual (true), Shared (False) | false | no | no |
| as-proxy | boolean | Sets the origin to the parent. | false | no | no |
| extra-limit | integer | when attaching (NOT refreshing) a cluster defined behaviour, adds to the limit you can apply | 0 | no | yes |
| ignore-limit | boolean | when attaching (NOT refreshing) a cluster defined behaviour, ignores the limit | false | no | no |
| behaviours | string | the keying (NOT the id) of behaviours as declared by the parent skill | | yes | no |
| inherit-data | boolean | will insert the pre-existing event data into the triggering of the attachment | false | no | no |