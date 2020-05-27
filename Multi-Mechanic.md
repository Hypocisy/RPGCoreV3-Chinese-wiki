A wrapper allowing you to execute multiple mechanics at once. **You cannot use the string form to load an action list** (only mechanics!) Mechanics are ran before actions.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | string | | multi | yes | no |
| mechanics | string list | ids under which the mechanics are keyed in the parent skill | | no | no |
| actions | string list or section | will behave like an extension of an action list of a behaviour | | no | no |