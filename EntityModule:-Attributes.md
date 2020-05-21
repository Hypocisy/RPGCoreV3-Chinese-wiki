Directory: "./../entitymodule/creatures"
Module: EntityModule

There is a number of hardcoded attributes which affect monsters. While most of these are meant to be entity attributes, a few of them also apply to players.

# Looting related attributes

When calculcating the effective attribute, the parameter from the configuration is introduced as a base value to every attribute listed below.

| Attribute | Description | Defaults |
|-|-|-|-|
| | | | |
| ITEM_QUANTITY | Quantity of items dropped | 0.0 |
| ITEM_FORTUNE | Re-roll chance for the item picked by a tag | 0.0 |
| ITEM_SKILL_DROP | Chance to drop a generic skill used by the mob | 0.0 |

# Threat related attributes

Threat affects both players and monsters, it becomes especially prevalent for summoner type players. Threat is designed in such a way that only the aggro of the target is stored, the mob will change targets once the threat hit zero.

Should your aggro rate be less then one you can avoid being focused by aggressive monsters. Should multiple targets be present, the one with the highest aggro rate will be picked as a target.

| Attribute | Description | Defaults |
|-|-|-|-|
| | | | |
| AGGRO_RANGE | relative to the mob, the range in which we will draw threat, limited to a maximum 16.0 | 8.0 |
| AGGRO_RATE | relative to the attacker, the multiplier to aggro generated. | 1.0 |

# Battle related attributes

Applies a multiplier of (1/(1+x)) to the combat rate of mobs, at one point this number will become useless as the number would be rounded down.

| Attribute | Description | Defaults |
|-|-|-|-|
| | | | |
| MOB_ATTACK_SPEED | a multiplier to the rate at which melee mobs attack | 0.0 |
| MOB_CAST_SPEED | a multiplier to the rate at which casters use spells | 0.0 |
| MOB_SHOOT_SPEED | a multiplier to the rate at which archers shoot bows | 0.0 |

# Summoning related attributes

This relates to the minion mechanic from the skill module.

The precise limit of mobs summoned is tied to the minion mechanic as-well, do not confuse the type limit with the limit of minions concurrently summoned.

| Attribute | Description | Defaults |
|-|-|-|-|
| | | | |
| MINION_TYPE_LIMIT | how many different types of minions can be summoned | 1 |
| AID_PARENT_ATTACK | When parent deals an attack, chance to target that entity | 0.0 |
| AID_PARENT_DEFEND | When parent takes an attack, chance to target that entity | 0.0 |