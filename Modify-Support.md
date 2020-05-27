The modify support refers to inserting a modifier like if it was on an supported link, this should be used with special care as it bleeds through varying event executions.

The modifiers listed in the "setup" section can resolve variables in their formula part!

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | string | | modify-support | yes | no |
| setup | modifier list | list of the modifiers to all supports | | yes | partial |
| baked | boolean | bake the variable to a static value so it wont calculcate again | false | no | no |