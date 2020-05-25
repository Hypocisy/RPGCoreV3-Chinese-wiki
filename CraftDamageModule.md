Directory: "./../CraftDamageModule.yml"  
Module: CraftDamageModule, DamageModule

This module stands in context with the DamageModule itself, it handles the things which are related to the minecraft aspect of damage such as mitigation of natural damage causes etc. You should not need to modify the mitigation table, however you may want to adjust the other parameters to fit your server better.

# Configuration

| Option | Type | Description |
|-|-|-|
| carry-minecraft-combat-damage | boolean | **prevents** normal (non rpgcore) items from dealing damage |
| default-melee-element | string | default element that attacking in melee inflicts |
| default-projectile-element | string | default element that attacking with bows inflicts |
| barehanded-modifiers | attribute modifiers | allows empty handed damage, adds "UNARMED" as a damage type. Beware that these are combat attirbutes, NOT entity attributes. |

# Hardcoded Behaviour

There is some hard coded behaviour of damage you cannot modify, the specifics are like following:

* If two entities are not considered hostile, they cannot attack each other 
* When both parties are players, the "PVP" damage type is added
* When one party is a player, the "PVE" damage type is added
* "Attacking" with weapons adds the "ATTACK" and "HIT" damage type
* Hitting from behind adds "BACKSTAB_RANGE" or "BACKSTAB_MELEE" as a damage type
* If the damage is not considered a BACKSTAB adds "NOT_BACKSTAB" as a damage type
* Projecitles add the "PROJECTILE" damage type
* Projectiles add the "PROJECTILE_\<type>" damage type, where type is the [entity type of the projectile](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/entity/EntityType.html)
* When hit attacked melee, the "MELEE" damage type is added 