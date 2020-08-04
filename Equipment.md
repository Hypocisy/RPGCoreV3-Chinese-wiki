Directory: "./../Equipment.yml"  
Module: Equipment

This allows you to setup additional slots for players to equip items in. You will hijack some inventory slots for this to work, there currently is no other way of putting this into use. Beneath you can see the respective id at the matching position.

# How to create additional equipment slots

Every slot can hold one piece of equipment, make sure the id of every slot is unique. Beware that the equipment piece has to receive the matching `RC_INV_TAG` nbt tag so that it can be equipped into the target slot.

| Option | Type | Description |
|-|-|-|
| displayname | string | displayname of slot in inventory |
| icon | material | a material:model string for the item to block the slot |
| accepted | string list | item tag which is required for the slot |
| slot-id | integer | [inventory slot](https://media.discordapp.net/attachments/514457413475237928/714519325758980137/unknown.png) which can be used to equip the item |