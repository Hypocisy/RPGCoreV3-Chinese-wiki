Beneath you can find a listing of all hardcoded attributes. Beware that this is **not** the list of all attributes, a massive chunk of attributes will instead be generated based on your server configuration.

## Hardcoded Exact Attributes

You will find the attributes which have **their full name fixed** listed here.

| Attribute | Type | Usage | Defaults | Module |
|-|-|-|-|-|
| EXP_GAIN_RATE | Entity | Multiplier to experience gained | 1.0 | [[LevelModule]] |
| EXP_GIVE_RATE | Entity | Multiplier to experience given | 1.0 | [[LevelModule]] |
| AFFIXEXPANSION | Entity | Multiplier to effects of affixes | 1.0 | [[ItemModule]] |
| SOCKETEXPANSION | Entity | Multiplier to effects of sockets | 1.0 | [[ItemModule]] |
| IMPLICITEXPANSION | Entity | Multiplier to effects of implicits | 1.0 | [[ItemModule]] |
| GLOBAL_BLOOD_MAGIC | Entity | When greater-equal 1, all skills have blood magic | 0.0 | [[SkillModule]] |
| LOCAL_BLOOD_MAGIC | Skill | When greater-equal 1, all linked skills have blood magic | 0.0 | [[SkillModule]] |
| ATTACK_SPEED | Entity | Applies a **multiplier** on [entity movement speed](https://minecraft.gamepedia.com/Attribute) | 0.0 | Internal |
| MOVEMENT_SPEED | Entity | Applies a **multiplier** on [player attack speed](https://minecraft.gamepedia.com/Attribute) | 0.0 | Internal |
| KNOCKBACK_TAKE | Entity | Currently not used | 1.0 | Internal |
| KNOCKBACK_GIVE | Entity | Currently not used | 1.0 | Internal |
| SOUL_DURATION | Entity | Ticks until souls start decaying | 600 | Internal |
| SOUL_AMOUNT | Entity | Maximum souls on an entity | 20 | Internal |
| SOUL_GIVE | Entity | Chance to give away a soul on kill | 0.1 | Internal |
| SOUL_TAKE | Entity | Chance to gain a soul on kill | 0.0 | Internal |
| DODGE_CHANCE | Entity | Chance to neutralize damage by dodge | 0.0 | [[DamageModule]] |
| BLOCK_CHANCE | Entity | Chance to neturalize damage by block | 0.0 | [[DamageModule]] |
| CULLING_CHANCE | Entity | Chance to instant kill target at low life | 0.0 | [[DamageModule]] |
| CULLING_THRESHOLD | Entity | Threshold to consider on low life | 0.1 | [[DamageModule]] |
| DODGE_CHANCE | Combat | Chance to neutralize damage by dodge | 0.0 | [[DamageModule]] |
| BLOCK_CHANCE | Combat | Chance to neturalize damage by block | 0.0 | [[DamageModule]] |
| CULLING_CHANCE | Combat | Chance to instant kill target at low life | 0.0 | [[DamageModule]] |
| CULLING_THRESHOLD | Combat | Threshold to consider on low life | 0.1 | [[DamageModule]] |
| CRIT_CHANCE | Combat | Chance for damage to be critical | 0.0 | [[DamageModule]] |
| CRIT_DAMAGE | Combat | Extra damage multiplier with crits | 0.0 | [[DamageModule]] |
| CRIT_DEFENSE | Combat | Less damage taken from crits | 0.0 | [[DamageModule]] |
| ITEM_QUANTITY | Entity | Quantity of items dropped, extra item per 100% | 0 | [[EntityModule]] |
| ITEM_FORTUNE | Entity | Select lower weighted item, extra roll per 100% | 0 | [[EntityModule]] |
| ITEM_SKILL_DROP | Entity | Drop generic skills used by monster | 0 | [[EntityModule]] |
| AGGRO_RANGE | Entity | Range in which mob picks enemies | 8 | [[EntityModule]] |
| AGGRO_RATE | Entity | Aggro multiplier, less then 1.0 = chance to be ignored | 1 | [[EntityModule]] |
| MINION_TYPE_LIMIT | Entity | Types of minions can be summoned at once | 1 | [[EntityModule]] |
| AID_PARENT_ATTACK | Entity | chance to target who is attacked by summoner | 0 | [[EntityModule]] |
| AID-PARENT_DEFEND | Entity | chance to target who is attacking summoner | 0 | [[EntityModule]] |
| MOB_ATTACK_SPEED | Entity | multiplier to rate at which melee attacks happen | 0 | [[EntityModule]] |
| MOB_CAST_SPEED | Entity | multiplier to rate at which spell casts happen | 0 | [[EntityModule]] |
| MOB_SHOOT_SPEED | Entity | multiplier to rate at which shooting bows happen | 0 | [[EntityModule]] |


## Hardcoded Generated Attributes

You will find the attributes which have **one part of their name fixed** listed here.

| Attribute | Type | Usage | Defaults | Module |
|-|-|-|-|-|
| CYCLE_# | Entity | Duration until a flag cycle updates | 80 | [[FlagModule]] |
| SKILL_# | Entity | Universal modifiers for an skill variable | 0 | [[SkillModule]] |
| SKILL_#:# | Entity | Tagged modifiers for an skill variable | 0 | [[SkillModule]] |
| GLOBAL_SKILL_LEVEL_# | Entity | Add to level of all skills, based on tag | 0 | [[SkillModule]] |
| LOCAL_SKILL_LEVEL_# | Skill | Add to level of linked skills, based on tag | 0 | [[SkillModule]] |
| #_AMOUNT | Entity | Health, Shield and Mana amount | 0 | Internal |
| #_FLAT | Entity | Health, Shield and Mana flat regeneration | 0 | Internal |
| #_PERCENT | Entity | Health, Shield and Mana percent regeneration | 0 | Internal |
| #_RECOVERY | Entity | Health, Shield and Mana out of combat percent regeneration | 0 | Internal |
| #_REGEN_EFFICIENCY | Entity | Health, Shield and Mana regeneration multiplier | 0 | Internal |
| OVERLEECH_DURATION_# | Entity | Health, Shield and Mana leech retaining when saturated | 0 | Internal |
| MAXIMUM_LEECH_AS_# | Entity | Health, Shield and Mana maximum leech per second | 0.2 | Internal |
| DEAL_#_AS_# | Entity | Attacker converts from element to element | 0.0 | [[DamageModule]] |
| TAKE_#_AS_# | Entity | Defender converts from element to element | 0.0 | [[DamageModule]] |
| LEECH_AS_#_# | Entity | Resource leeched from element | 0.0 | [[DamageModule]] |
| INSTANT_LEECH_AS_#_# | Entity | Instant resource leeched from element | 0.0 | [[DamageModule]] |
| DEAL_#_AS_# | Combat | Attacker converts from element to element | 0.0 | [[DamageModule]] |
| TAKE_#_AS_# | Combat | Defender converts from element to element | 0.0 | [[DamageModule]] |
| LEECH_AS_#_# | Combat | Resource leeched from element | 0.0 | [[DamageModule]] |
| INSTANT_LEECH_AS_#_# | Combat | Instant resource leeched from element | 0.0 | [[DamageModule]] |
| CRIT_CHANCE_# | Entity | Chance for type damage to be critical | 0.0 | [[DamageModule]] |
| CRIT_DAMAGE_# | Entity | Extra damage multiplier with type crits | 0.0 | [[DamageModule]] |
| CRIT_DEFENSE_# | Entity | Less damage taken from type  crits | 0.0 | [[DamageModule]] |

