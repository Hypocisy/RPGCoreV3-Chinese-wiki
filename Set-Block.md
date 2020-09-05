Updates the world in realtime, beware that this is not meant for high intensity processing and may cause lasting changes to your world. **This will not be running any authorization checks.** Mainly intended to be used with absolute targetters. Again, this will modify the world without any checks done - this includes any important builds. **This is not tracked in any form either.**

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | string | | chat | yes | no |
| physics | boolean | update the physics after changing | false | no | no |
| material-distribution | material:weight list | a list of materials with weights, will pick a random one to update | | yes | no |