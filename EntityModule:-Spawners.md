Directory: "./../entitymodule/spawners"  
Module: EntityModule

The filename should match with your world name, RPGCore then will handle the spawning within that world. It is recommended that you disable natural spawning rules, as only rpgcore mobs interact with rpgcore. Avoid mob stacking plugins.

It is recommended to disable natural mob spawning when using RPGCore, you can do this using the mob spawning [gamerule](https://minecraft.gamepedia.com/Commands/gamerule)

| Option | Type | Description | Defaults |
|-|-|-|-|
| world-spawn-interval | integer | interval at which we update the mob spawning | required |
| world-spawn-range | integer | chunk range to cause static spawns to be populated | required |

# Static Configuration

You will need to specify every single spawner location manually should you define it from here.

| Option | Type | Description | Defaults |
|-|-|-|-|
| | | | |
| location | locations | a list of specific locations that can spawn a mob | required |
| spawn-chance | percentage | a chance for a player to cause spawning here | required |
| spawn-limit | integer | maximum mobs to concurrently be spawned per location | required |
| spawn-level | integer | level of mobs spawned at the locations | required |
| spawnable | weighting | mapping of mob ids to weights, will roll a random mob to spawn | required |

```yml
  'Vagabond Spawner #2':
    # Spawn position that is used by the mob (Spawns right above position)
    location: 
    - "103 58 588"
    - "125 54 111"
    - "585 88 144"
    # Chance when we are ticked that we spawn
    spawn-chance: 10%
    # Up to 3 Vagabonds may spawn from this point
    spawn-limit: 3
    # Level at which the mobs shall spawn
    spawn-level: 3
    # You may list multiple possible spawns here where the value assigned is the weight.
    spawnable:
      UNDYING_VAGABOND: 1
```

# Random Configuration

Spawners defined here are all isolated from each other, every player will attempt to tick every rule. 

If you want mobs to spawn on the floor use the "**GROUNDED**" required-state.  
If you want mobs to spawn in liquid use the "**SUBMERGED**" required-state.  
If you want mobs to spawn at the bottom of liquid use the "**FLOODED**" required-state.

The random points are sampled at a distance of 32 to 64 blocks from a player, but the position on the y axis is a bit flatter.

| Option | Type | Description | Defaults |
|-|-|-|-|
| | | | |
| spawn-chance | percentage | a chance for a player to tick the spawner rule | required |
| spawn-attempts | integer | number of attempts to spawn something before giving up | required |
| spawn-limit | integer | number of mobs from this spawner that can populate one chunk | required |
| spawn-count | decimal | number of mobs to spawn at once, less then 1.0 is a chance for extra mobs | require |
| spawn-level | integer | basic level added to all spawned mobs | required |
| level-scaling-by-distance | integer | add levels based on distance from 0/0, 0 to disable | required |
| maximum-density | integer | maximum mobs from this rule in a 8x8 range around one player | required |
| require-state | spawner state | the specific type of a position we want to have | required |
| deny-spawn-if-failed | targetter list | runs this layered targetter on the mob, despawning if no target remains | required |
| spawnable-random | weighting | mapping of mob ids to weights, will roll a random mob to spawn | required |

```yml
  'Vagabond R-Spawner #1':
    # 15% chance for a player to cause mob spawning.
    spawn-chance: 15%
    # 10 attempts to find a location suitable for mob spawning
    spawn-attempts: 10
    # 0~3 mobs from this spawner can populate one chunk
    spawn-limit: 3
    # When random spawning, 100% chance for 1 mob, 30% for one additional mob.
    spawn-count: 1.3
    # 3 levels added to the spawned mobs
    spawn-level: 3
    # Maximum mobs from this spawner in an 8x8 area around the sampled player
    maximum-density: 10
    # 1 level added per 500 blocks, disable with negative number.
    level-scaling-by-distance: 500
    # Accepted: "GROUNDED" (Solid, Air, Air) 
    # Accepted: "SUBMERGED" (Liquid, Liquid, Liquid)
    # Accepted: "FLOODED" (Solid, Liquid, Any) 
    # Accepted: "NONE" to ignore the condition.
    require-state: GROUNDED
    # Despawns the mob after spawning it, checking if it meets conditions.
    deny-spawn-if-failed:
    - 'material{should-be=["-1:GRASS_BLOCK|SAND"]}'
    # The pool of mobs which can be spawned from this, weighted.
    spawnable-random:
      CRACK_SHOOTER: 1
      BURNING_SOUL: 1
      UNDYING_VAGABOND: 4
```
