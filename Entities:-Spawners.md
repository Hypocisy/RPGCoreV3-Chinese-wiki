Directory: "./../Entities"  
Module: Entities

The filename should match with your world name, RPGCore then will handle the spawning within that world. It is recommended that you disable natural spawning rules, as only rpgcore mobs interact with rpgcore. Avoid mob stacking plugins.

It is recommended to disable natural mob spawning when using RPGCore, you can do this using the mob spawning [gamerule](https://minecraft.gamepedia.com/Commands/gamerule) - RPGCore is not meant to be used with any mobs except for rpgcore mobs. 

Mob spawning ocurrs on a per-chunk basis, the chunk a player is in specifically. We pick a chunks 16-80 blocks around the player, however the y axis is somewhat flatter in that regard -32 to +32 blocks. When a chunk cannot be populated once, it won't be attempted to be populated again. Hence, complicated and narrow terrain may require you to define manual spawning points for reliable spawning.

# Exact Mob Spawning

Spawns mob on an exact specified location. These spawnrules are grouped per cuboid chunk (16x16x16), no exact spawner will trigger should any of the spawners have a living mob. If you have narrow/tight structures, I do recommend to populate them with exact spawner rules as the random spawner rules are very likely to populate these extremely sparsely.

| Option | Type | Description | Defaults |
|-|-|-|-|
| | | | |
| location | locations | a list of specific locations that can spawn a mob | required |
| spawn-chance | percentage | the chance for this spawnrule to trigger | required |
| spawn-limit | integer | maximum mobs to concurrently be spawned per location | required |
| spawn-level | integer | level of mobs spawned at the locations | required |
| spawnable | weighting | mapping of mob ids to weights, will roll a random mob to spawn | required |

# Random Mob Spawning

Generates a subset of random locations which can be populated by itself. You can check out the [Worldguard] extension to include region filtering on your zones. You can enhance your performance by quite a lot if you limit your spawnrules within worldguard zones. Within the same 16³ chunk, ensure that you have the same worldguard regions. Having more players can speed up respawning to a limited degree (Raise spawn chance & Sample additional chunks.) but it will **not** raise the maximum density of mobs spawned.

If you want mobs to spawn on the floor use the "**GROUNDED**" required-state.  
If you want mobs to spawn in liquid use the "**SUBMERGED**" required-state.  
If you want mobs to spawn at the bottom of liquid use the "**FLOODED**" required-state.

| Option | Type | Description | Defaults |
|-|-|-|-|
| | | | |
| spawn-chance | percentage | the chance for this spawn rule to trigger | required |
| spawn-attempts | integer | sample random locations in a 16³ chunk, however no more then 3 locations are picked per 16³ | required |
| spawn-limit | integer | every 1.0 represents a 100% chance for +1 max mob in the entire chunk, avoid high numbers | required |
| spawn-level | integer | adds a number of levels to the spawned mob | required |
| level-scaling-by-distance | integer | add levels based on distance, use 0 to disable | required |
| level-scaling-origin | coordinate | center of level scaling control | required |
| require-state | spawner state | the specific type of a position we want to have | required |
| deny-spawn-if-failed | targetter list | runs this layered targetter on the mob, despawning if no target remains | required |
| spawnable-random | weighting | mapping of mob ids to weights, will roll a random mob to spawn | required |
| region-requirement | string list | worldguard region ids which can apply this spawner, make sure that a 16³ chunk has the same region at all points. | required |
| block-requirement | section | y-axis offset mapped to materials, empty for dont care | required | 
| boss-spawns | section | boss spawning confiruation | required |

# Boss Configuration

A boss is spawned after a certain number of mobs are killed from the spawner, the spawn location is simply hijacking one random spawner iteration. You cannot spawn another boss while one is alive from the same boss rule.

| Option | Type | Description | Defaults |
|-|-|-|-|
| | | | |
| boss-choices | weighting | boss id to spawning weight | required |
| cooldown | ticks | boss cannot respawn for X ticks after being killed | required |
| requirement | integer | how many mobs have to die to spawn a boss | required |
| extra-level | integer | additional levels added for the boss | required |
| broadcast | string list | boss spawning broadcast to notify about the spawn | requried |