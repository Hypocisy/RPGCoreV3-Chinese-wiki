Check if the given equipment slot has an item with the given item id

By default RPGCore has the following equipment slots: MAIN_HAND, OFF_HAND, HELMET, CHEST, LEGS, BOOTS but the [[AdvancedEquipmentModule]] may add some more.

Using item slot "AUTO" will instead pick the slot the item originates from, if no item is found it evaluates to true.

Prefixing the item slot with "TARGET_" or "PARENT_" will instead check the items of the said entity. By default it aims at who called the condition (Alias "SELF") This will not work if using "AUTO"

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | / | / | equipped | / | / |
| slot | Item Slot | The slot we are checking | AUTO | no | no |
| allowed | Item Id List | List of item ids that are allowed | / | yes | no |