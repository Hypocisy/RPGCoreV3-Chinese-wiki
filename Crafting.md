Directory: "./../Crafting.yml"  
Module: Crafting

This module permits you to left click on an item while holding a certain [[ItemModule: Materials]] to modify the said item.

# How to create additional equipment slots

Every slot can hold one piece of equipment, make sure the id of every slot is unique. Beware that the equipment piece has to receive the matching `RC_INV_TAG` nbt tag so that it can be equipped into the target slot.

| Option | Type | Description |
|-|-|-|
| incompatible-material | string | material cannot be applied |
| successful-applied | string | application was successful |
| failure-applied | string | application has failed |
| item-broken | string | application and breaking roll failed |
| item-protected | string | was meant to break, but was protected |
| chance-to-break-on-fail | percent | chance for the upgrade to break the item |