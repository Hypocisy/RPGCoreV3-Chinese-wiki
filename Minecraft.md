Directory: "./../Minecraft.yml"  
Module: Minecraft

## Bossbar (Enemy Health)

This is **disabled** by default, when enabled you will see the health of the last attacked enemy as a bossbar. Please note that there are multiple bossbars already in use (Offhand, Status effects) so you will end up with a really cluttered screen.

The following colors are available: BLUE, GREEN, AQUA, RED, PURPLE, YELLOW, WHITE, BLACK

| Option | Type | Description |
|-|-|-|
| health-color | coloring | coloring of the health piece |
| shield-color | coloring | coloring of the shield piece |
| name-mapping | string | when lacking a name, use these mappings |

# Damage (Natural Causes)

Damage which is caused from natural minecraft sources.

| Option | Type | Description |
|-|-|-|
| carry-minecraft-combat-damage | boolean | **prevents** normal (non rpgcore) items from dealing damage |
| default-melee-element | string | default element that attacking in melee inflicts |
| default-projectile-element | string | default element that attacking with bows inflicts |
| barehanded-modifiers | attribute modifiers | allows empty handed damage, adds "UNARMED" as a damage type. Beware that these are combat attirbutes, NOT entity attributes. |

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

# Experience Bar

Handle rpgcore levels shown on the minecraft exp bar of the player.