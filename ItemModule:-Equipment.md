Directory: "./../itemmodule/items"  
Module: ItemModule

Items created from within RPGCore can affect players and monsters alike. There is no differentiation between a player having an item, and a mob having an item. 

However, beware that monsters may not have the same equipment slots as players (iE: Accessories may not be equipable!)

# Configuration (./../itemmodule/items) - Items

This covers general item configuration, equipment still may need to specify the options defined here.

| Option | Type | Description |
|-|-|-|
| amount | integer | amount to set to |
| durability | integer | durability to set to |
| unbreakable | boolean | mark the item as unbreakable |
| flags | list of flags | [ItemFlag](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/ItemFlag.html) to add to the created item copy |
| material | material | the minecraft material to use for this item |
| name | string | displayname of the item, may be further modified |
| lore | string list | mostly meant for flavor texts|
| rarity | rarity | explicit rarity or rarity weighing, can be undefined |
| seed | boolean | seed the item randomly, the RANGE function needs a seeded item |
| implicits | attribute list | always available attributes for the item |
| custom-tags | section | nbt data to write on the spawned item |
| leather-color | integer | integer or hexadecimal for leather color |
| potion-color | integer | integer or hexadecimal for potion color | 
| skull | skull encoding | https://minecraft-heads.com/ "value" |
| consumable | skill configuration | a locally defined skill with a consumer trigger |
| custom-model | integer | pre-1.14 will be unbreakable+durability, 1.14+ will be custom model override. |

# Configuration (./../itemmodule/items) - Equipment

This covers general item configuration, equipment still may need to specify the options defined here.

| Option | Type | Description |
|-|-|-|
| color-weighing | color-integer | the weighing used when rolling the color arrangement |
| local-data.affixing-pool | string | affixing pool to use when rolling for affixes |
| local-data.main-skills | skill:level list | socketed skills will support these skills |
| local-data.support-skills | skill:level list | socketed skills are supported by these skills |
| local-data.link-state | string | local value using 0 and 1 to represent the skill linking state (locked/unlocked) |
| local-data.default-upgrade-cap | integer | upper limit of upgrading for this item |

# Combat modifiers for weapons

Note that these parameters can be present on arrows too and will overlap with the modifiers present on the bow.

| keyword | type | description |
|-|-|-|
| combat.melee-elements | string list | replace the default element that is dealt by this weapon |
| combat.melee-modifiers | attribute list | written like attributes, but processed by the damage module |
| combat.melee-types | string list | adds additional types when using this weapon, does not override. |
| combat.range-elements | string list | replace the default element that is dealt by this weapon |
| combat.range-modifiers | modifier list | written like attributes, but processed by the damage module |
| combat.range-types | modifier list | adds additional types when using this weapon, does not override|
