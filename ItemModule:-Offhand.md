Directory: "./../itemmodule/items"  
Module: ItemModule, SkillModule

Offhand tools are a specialized way of interacting with rpgcore, you may only have one of them active at a time. Beware that only the RPGCore item itself will open up these capacities. **The offhand item will only grant you the benefits if it is equipped to your offhand.**

Note that the configurations documented here refer to nbt tags on the offhand items.

Check out [[SkillModule: Variables]] there are some variables which are related to certain offhand sub types. 

Check out [[SkillModule: Triggers]] there are some triggers which are related to certain offhand sub types.

## Offhand Tool: Shield

Using a shield opens up "Blocking Power", the resource is recovered when your shield is lowered and consumed when your shield is raised. When you exhaust your blocking power, your shield will be put on a cooldown. The blocking power will absorb all damage, so long you have sufficient amounts of it.

Blocking from the "BLOCK_CHANCE" attribute and blocking from raising your shield will both be adding the "BLOCKED" to the damage interactions you have suffered.

| Keyword | Type | Description |
|-|-|-|
| shield-absorption | integer | flat amount of blocking power to receive |
| shield-absorption-percent | percentage | relative amount of blocking power to health and shield |
| shield-recovery | percentage | percentage of blocking power to recover per second while shield is lowered |
| shield-decay | percentage | percentage of blocking power to lose per second while shield is raised |
| shield-targets | damage type list | a specific list of damage types that can be blocked |

## Offhand Tool: Spellbook

Using a spell book opens up the ability to cast spells. Using a permutation of actions (Left click, Right click, Drop Item, Switch item) will allow you to selectively cast a certain spell. Note that "spells" are referring to skills which are setup to be casted with this.

This is meant to be used in context with the `cast` trigger, beware that damage inflicted by the cast trigger will add "SELF_CAST" as a damage type.

| Keyword | Type | Description |
|-|-|-|
| skill-modifiers | attribute list | extra modifiers for skill parameters, does not access entity |

## Offhand Tool: Totem

Using a totem opens up the ability to summon a totem to use your spells in your place. The skill socketed on the totem will be used by it, until it runs out of summoning time. Beware that totems using skills are like you using the skills, hence you are receiving the aggro of a totem.

This is meant to be used in context with the `totem` trigger, beware that damage inflicted by the totem trigger will add "TOTEM" as a damage type. Players hitting the totem in melee will cause it to run out of summoning time even faster.

| Keyword | Type | Description |
|-|-|-|
| skill-modifiers | attribute list | extra modifiers for skill parameters, does not access entity |

## Offhand Tool: Trap

Using a trap opens up the ability to place a trap to use your spells in your place. The skill socketed on the trap will be used by it once the trap is triggered. Beware that traps using skills are like you using the skills, hence you are receiving the aggro of a trap.

Traps are worked of in the sequence they are triggered, at an interval of 0.1 seconds. Traps are triggered if a target is close enough, the placing player has hit the crouching button or they ran out of duration.

This is meant to be used in context with the `trap` trigger, beware that damage inflicted by the trap trigger will add "TRAP" as a damage type. 

| Keyword | Type | Description |
|-|-|-|
| skill-modifiers | attribute list | extra modifiers for skill parameters, does not access entity |