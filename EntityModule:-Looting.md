Directory: "./../entitymodule/creatures", "./../itemmodule/items"  
Module: EntityModule, ItemModule  

Looting is based on tagging. Every item in RPGCore is meant to be tagged. While this makes drops rather random, it will save you from defining large looting tables for every mob.

When a mob drops an item, it first rolls a tag. When it picked a tag, it will select a random item which is subscribed to that tag. It may re-roll the item based on the fortune, trying to pick the rarest outcome. This repeats until the item quantity is exhausted.

# Tagging an item

This is an option within the configuration of an item, you can define a unique tag to an item if you want to cause a specific item to be dropping.

| Option | Type | Description | Defaults |
|-|-|-|-|
| | | | |
| dropable.weight | double | the chance to drop this specific item when rolling the tag | required |
| dropable.level | integer | minimum level for this item to drop when rolling the tag | required |
| dropable.tagging | tag list | list of tags that the item will subscribe to | required |

# Setting up a loot table

This is an option within the configuration of an mob. Quantity and fortune can be level scaled using the mob attributes.

| Option | Type | Description | Defaults |
|-|-|-|-|
| | | | |
| loot-table.drop-skill-chance | percentage | a chance to drop one of the skills used by the mob. Cannot drop unique skills defined within the mob configuration | required |
| loot-table.custom-loot-table.item-quantity | percentage | quantity of items dropped, every 100% is a guaranteed item | required |
| loot-table.custom-loot-table.item-fortune | percentage | re-roll the item choice to pick the one with the lowest weight, this will not re-roll the tag itself only the items subscribed to the tag | required |
| loot-table.custom-loot-table.loot-table-tags | section | a tag mapped to its weight, the same tag can be rolled multiple times | required |