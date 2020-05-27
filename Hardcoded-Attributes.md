Beneath you can find a listing of all hardcoded attributes. Beware that this is **not** the list of all attributes, a massive chunk of attributes will instead be generated based on your server configuration.

## Hardcoded Exact Attributes

You will find the attributes which have **their full name fixed** listed here.

| Attribute | Type | Usage | Defaults |
|-|-|-|-|
| EXP\_GAIN\_RATE | Entity | Multiplier to experience gained | 1.0 |
| EXP\_GIVE\_RATE | Entity | Multiplier to experience given | 1.0 |
| AFFIXEXPANSION | Entity | Multiplier to effects of affixes | 1.0 |
| SOCKETEXPANSION | Entity | Multiplier to effects of sockets | 1.0 |
| IMPLICITEXPANSION | Entity | Multiplier to effects of implicits | 1.0 |
| GLOBAL\_BLOOD\_MAGIC | Entity | use bloodmagic for all skills | 0.0 |
| LOCAL\_BLOOD\_MAGIC | Skill | use bloodmagic for linked skills | 0.0 |
| ATTACK\_SPEED | Entity | Applies a **modifier** on [movement speed](https://minecraft.gamepedia.com/Attribute) | 0.0 |
| MOVEMENT\_SPEED | Entity | Applies a **modifier** on [attack speed](https://minecraft.gamepedia.com/Attribute) | 0.0 |
| KNOCKBACK\_TAKE | Entity | Currently not used | 1.0 |
| KNOCKBACK\_GIVE | Entity | Currently not used | 1.0 |
| SOUL\_DURATION | Entity | Ticks until souls start decaying | 600 |
| SOUL\_AMOUNT | Entity | Maximum souls on an entity | 20 |
| SOUL\_GIVE | Entity | Chance to give away a soul on kill | 0.1 |
| SOUL\_TAKE | Entity | Chance to gain a soul on kill | 0.0 |
| DODGE\_CHANCE | Entity | Chance to neutralize damage by dodge | 0.0 |
| BLOCK\_CHANCE | Entity | Chance to neturalize damage by block | 0.0 |
| CULLING\_CHANCE | Entity | Chance to instant kill target at low life | 0.0 |
| CULLING\_THRESHOLD | Entity | Threshold to consider on low life | 0.1 |
| DODGE\_CHANCE | Combat | Chance to neutralize damage by dodge | 0.0 |
| BLOCK\_CHANCE | Combat | Chance to neturalize damage by block | 0.0 |
| CULLING\_CHANCE | Combat | Chance to instant kill target at low life | 0.0 |
| CULLING\_THRESHOLD | Combat | Threshold to consider on low life | 0.1 |
| CRIT\_CHANCE | Combat | Chance for damage to be critical | 0.0 |
| CRIT\_DAMAGE | Combat | Extra damage multiplier with crits | 0.0 |
| CRIT\_DEFENSE | Combat | Less damage taken from crits | 0.0 |
| ITEM\_QUANTITY | Entity | Quantity of items dropped, | 0 |
| ITEM\_FORTUNE | Entity | Select lower weighted item | 0 |
| ITEM\_SKILL\_DROP | Entity | Drop generic skills used by monster | 0 |
| AGGRO\_RANGE | Entity | Range in which mob picks enemies | 8 |
| AGGRO\_RATE | Entity | Aggro multiplier, less then 1.0 = chance to be ignored | 1 |
| MINION\_TYPE\_LIMIT | Entity | Types of minions can be summoned at once | 1 |
| AID\_PARENT\_ATTACK | Entity | attack parent target | 0 |
| AID-PARENT\_DEFEND | Entity | attack parent assaulter| 0 |
| MOB\_ATTACK\_SPEED | Entity | melee attack rate | 0 |
| MOB\_CAST\_SPEED | Entity | spell casts rate | 0 |
| MOB\_SHOOT\_SPEED | Entity | shooting bows rate | 0 |


## Hardcoded Generated Attributes

You will find the attributes which have **one part of their name fixed** listed here.

| Attribute | Type | Usage | Defaults |
|-|-|-|-|
| CYCLE\_# | Entity | Duration until a flag cycle updates | 80 |
| SKILL\_# | Entity | Universal modifiers for an skill variable | 0 |
| SKILL\_#:# | Entity | Tagged modifiers for an skill variable | 0 |
| GLOBAL\_SKILL\_LEVEL\_# | Entity | Add to level of all skills, based on tag | 0 |
| LOCAL\_SKILL\_LEVEL\_# | Skill | Add to level of linked skills, based on tag | 0 |
| #\_AMOUNT | Entity | amount | 0 |
| #\_FLAT | Entity | flat regeneration | 0 |
| #\_PERCENT | Entity | percent regeneration | 0 |
| #\_RECOVERY | Entity | out of combat percent regeneration | 0 |
| #\_REGEN\_EFFICIENCY | Entity | regeneration multiplier | 0 |
| OVERLEECH\_DURATION\_# | Entity | leech retaining when saturated | 0 |
| MAXIMUM\_LEECH\_AS\_# | Entity | maximum leech per second | 0.2 |
| DEAL\_#\_AS\_# | Entity | Attacker converts from element to element | 0.0 |
| TAKE\_#\_AS\_# | Entity | Defender converts from element to element | 0.0 |
| LEECH\_AS\_#\_# | Entity | Resource leeched from element | 0.0 |
| INSTANT\_LEECH\_AS\_#\_# | Entity | Instant resource leeched from element | 0.0 |
| DEAL\_#\_AS\_# | Combat | Attacker converts from element to element | 0.0 |
| TAKE\_#\_AS\_# | Combat | Defender converts from element to element | 0.0 |
| LEECH\_AS\_#\_# | Combat | Resource leeched from element | 0.0 |
| INSTANT\_LEECH\_AS\_#\_# | Combat | Instant resource leeched from element | 0.0 |
| CRIT\_CHANCE\_# | Entity | Chance for type damage to be critical | 0.0 |
| CRIT\_DAMAGE\_# | Entity | Extra damage multiplier with type crits | 0.0 |
| CRIT\_DEFENSE\_# | Entity | Less damage taken from type  crits | 0.0 |

