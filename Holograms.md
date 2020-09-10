Directory: "./../Holograms.yml"  
Module: Holograms

# Damage Indicator Holograms

When entities take damage, holograms will spawn for these numbers.

| Option | Type | Description |
|-|-|-|
| damage-color-avoided | string | indicator color for avoided damage |
| damage-color-received | string | indicator color for received damage |
| damage-color-critical | string | indicator color for critical damage |

# Entity Hologram

There is no configuration available for this module, the components are inherited from the definition of outer sources. These are mounted to all entites active in RPGCore.

| Hologram | Position | Content |
|-|-|-|
| Name | 0 | Name and level, if hostile/friendly will be colored red/green |
| Status Effects | 1 | Status effect icons of the entity |
| Health | 2 | Healthbar with energy shield, but no mana |
| Title | 3 | Title of a player, as defined by commands |
| Owner | 4 | Shown by mobs if they were summoned rather then spawned |
| Guild | 5 | If installed, can be used to show the guild of a player |
| Duration | 6 | Shown by mobs if they were summoned rather then spawned |