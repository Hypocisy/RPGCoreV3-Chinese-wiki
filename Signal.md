Called when the entity receives a signal

If among the actions executed by this trigger is a damage mechanic, it will be manually inserted with a "TRIGGERED" damage type. Additionally, all variables will receive a sub type of ":TRIGGERED"

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | string | | signal | yes | no |
| channel | string | channel to listen | | yes | no |
| inherit-supports | boolean | inherit manually inserted supports | no | no | no |
| inherit-tags | boolean | inherit the tags stored within the event | no | no | no |