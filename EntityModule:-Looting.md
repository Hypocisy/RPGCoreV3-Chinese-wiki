Directory: "./../entitymodule/creatures", "./../itemmodule/items"  
Module: EntityModule, ItemModule  

Looting is based on tagging. Every item in RPGCore is meant to be tagged. While this makes drops rather random, it will save you from defining large looting tables for every mob.

When a mob drops an item, it first rolls a tag. When it picked a tag, it will select a random item which is subscribed to that tag. It may re-roll the item based on the fortune, trying to pick the rarest outcome. This repeats until the item quantity is exhausted.

Should a mob be summoned by a skill, it will not be able to drop any items.

# Dropping an item (ItemModule)

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

# Custom Looting Implementation

You can define a number of custom loots. Items are not considered custom loot, when saying "custom" loots it refers to things like commands, passive points, refunding points, instant power-ups and similar. 

Custom loot is written in the `./EntityModule/looting` directory, every file in the directory is scanned.

| Option | Type | Description | Defaults |
|-|-|-|-|
| | | | |
| type | string | reward type id | required |
| weight | double | the chance to drop this reward | required |
| level | integer | minimum level for this reward | required |
| tagging | tag list | list of tags that the reward will subscribe to | required |

***

## Custom Looting: Command

The command variable '{0}' is resolved to the player name, '{1}' is resolved into the player uuid!

| Option | Type | Description | Defaults |
|-|-|-|-|
| | | | |
| type | string | reward type: command | required |
| command | string | command to execute | required |
| operator | boolean | execute reward as an operator | false |
| server | boolean | execute reward over console | false |

## Custom Looting: Powerup

Grants temporary access to a certain behaviour, the logic used is identical to the [[Attachment]] mechanic. Only the behaviours which are tagged as `powerup: true` are granted to the player, **not** the primary behaviours!

| Option | Type | Description | Defaults |
|-|-|-|-|
| | | | |
| type | string | reward type: powerup | required |
| powerup | section | a **complete** skill that is the power-up | required |
| duration | integer | duration in ticks of the power-up  | 1200 |
| stacks | integer | maximum stacks of the power-up gained | 1 |
| individual | boolean | use individual stack counting | false |

## Custom Looting: Refund Points

Grants players access to refunding points on the passive tree. **Warning!** This will result in an infinite amount of refunding points, the limit refers to how many points the player may have at the current time. Design the drop rate of these accordingly!

| Option | Type | Description | Defaults |
|-|-|-|-|
| | | | |
| type | string | reward type: refunding | required |
| amount | integer | total of refunding points given | 1 |
| group | string | the passive point type | default | 
| limit | integer | maximum amount of refund points | 10 |

## Custom Looting: Passive Points

Grants players access to **one** passive point, however should they have the "limit" tag they will not gain it again.

| Option | Type | Description | Defaults |
|-|-|-|-|
| | | | |
| type | string | reward type: passive | required |
| group | string | the passive point type | default | 
| limit | string | cannot gain again if we got the tag | required |