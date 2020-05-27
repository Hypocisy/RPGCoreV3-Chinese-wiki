Beneath you can find a listing of all hardcoded attributes. Beware that this is **not** the list of all attributes, a massive chunk of attributes will instead be generated based on your server configuration.

## Hardcoded Exact Attributes

You will find the attributes which have **their full name fixed** listed here.

| Attribute | Type | Usage | Defaults |
|-|-|-|-|
| EXP_GAIN_RATE | Entity | Multiplier to experience gained | 1.0 |
| EXP_GIVE_RATE | Entity | Multiplier to experience given | 1.0 |
| AFFIXEXPANSION | Entity | Multiplier to effects of affixes | 1.0 |
| SOCKETEXPANSION | Entity | Multiplier to effects of sockets | 1.0 |
| IMPLICITEXPANSION | Entity | Multiplier to effects of implicits | 1.0 |
| GLOBAL_BLOOD_MAGIC | Entity | use bloodmagic for all skills | 0.0 |
| LOCAL_BLOOD_MAGIC | Skill | use bloodmagic for linked skills | 0.0 |
| ATTACK_SPEED | Entity | Applies a **modifier** on [movement speed](https://minecraft.gamepedia.com/Attribute) | 0.0 |
| MOVEMENT_SPEED | Entity | Applies a **modifier** on [attack speed](https://minecraft.gamepedia.com/Attribute) | 0.0 |
| KNOCKBACK_TAKE | Entity | Currently not used | 1.0 |
| KNOCKBACK_GIVE | Entity | Currently not used | 1.0 |
| SOUL_DURATION | Entity | Ticks until souls start decaying | 600 |
| SOUL_AMOUNT | Entity | Maximum souls on an entity | 20 |
| SOUL_GIVE | Entity | Chance to give away a soul on kill | 0.1 |
| SOUL_TAKE | Entity | Chance to gain a soul on kill | 0.0 |
| DODGE_CHANCE | Entity | Chance to neutralize damage by dodge | 0.0 |
| BLOCK_CHANCE | Entity | Chance to neturalize damage by block | 0.0 |
| CULLING_CHANCE | Entity | Chance to instant kill target at low life | 0.0 |
| CULLING_THRESHOLD | Entity | Threshold to consider on low life | 0.1 |
| DODGE_CHANCE | Combat | Chance to neutralize damage by dodge | 0.0 |
| BLOCK_CHANCE | Combat | Chance to neturalize damage by block | 0.0 |
| CULLING_CHANCE | Combat | Chance to instant kill target at low life | 0.0 |
| CULLING_THRESHOLD | Combat | Threshold to consider on low life | 0.1 |
| CRIT_CHANCE | Combat | Chance for damage to be critical | 0.0 |
| CRIT_DAMAGE | Combat | Extra damage multiplier with crits | 0.0 |
| CRIT_DEFENSE | Combat | Less damage taken from crits | 0.0 |
| ITEM_QUANTITY | Entity | Quantity of items dropped, | 0 |
| ITEM_FORTUNE | Entity | Select lower weighted item | 0 |
| ITEM_SKILL_DROP | Entity | Drop generic skills used by monster | 0 |
| AGGRO_RANGE | Entity | Range in which mob picks enemies | 8 |
| AGGRO_RATE | Entity | Aggro multiplier, less then 1.0 = chance to be ignored | 1 |
| MINION_TYPE_LIMIT | Entity | Types of minions can be summoned at once | 1 |
| AID_PARENT_ATTACK | Entity | attack parent target | 0 |
| AID-PARENT_DEFEND | Entity | attack parent assaulter| 0 |
| MOB_ATTACK_SPEED | Entity | melee attack rate | 0 |
| MOB_CAST_SPEED | Entity | spell casts rate | 0 |
| MOB_SHOOT_SPEED | Entity | shooting bows rate | 0 |


## Hardcoded Generated Attributes

You will find the attributes which have **one part of their name fixed** listed here.

| Attribute | Type | Usage | Defaults |
|-|-|-|-|
| CYCLE_# | Entity | Duration until a flag cycle updates | 80 |
| SKILL_# | Entity | Universal modifiers for an skill variable | 0 |
| SKILL_#:# | Entity | Tagged modifiers for an skill variable | 0 |
| GLOBAL_SKILL_LEVEL_# | Entity | Add to level of all skills, based on tag | 0 |
| LOCAL_SKILL_LEVEL_# | Skill | Add to level of linked skills, based on tag | 0 |
| #_AMOUNT | Entity | amount | 0 |
| #_FLAT | Entity | flat regeneration | 0 |
| #_PERCENT | Entity | percent regeneration | 0 |
| #_RECOVERY | Entity | out of combat percent regeneration | 0 |
| #_REGEN_EFFICIENCY | Entity | regeneration multiplier | 0 |
| OVERLEECH_DURATION_# | Entity | leech retaining when saturated | 0 |
| MAXIMUM_LEECH_AS_# | Entity | maximum leech per second | 0.2 |
| DEAL_#_AS_# | Entity | Attacker converts from element to element | 0.0 |
| TAKE_#_AS_# | Entity | Defender converts from element to element | 0.0 |
| LEECH_AS_#_# | Entity | Resource leeched from element | 0.0 |
| INSTANT_LEECH_AS_#_# | Entity | Instant resource leeched from element | 0.0 |
| DEAL_#_AS_# | Combat | Attacker converts from element to element | 0.0 |
| TAKE_#_AS_# | Combat | Defender converts from element to element | 0.0 |
| LEECH_AS_#_# | Combat | Resource leeched from element | 0.0 |
| INSTANT_LEECH_AS_#_# | Combat | Instant resource leeched from element | 0.0 |
| CRIT_CHANCE_# | Entity | Chance for type damage to be critical | 0.0 |
| CRIT_DAMAGE_# | Entity | Extra damage multiplier with type crits | 0.0 |
| CRIT_DEFENSE_# | Entity | Less damage taken from type  crits | 0.0 |

