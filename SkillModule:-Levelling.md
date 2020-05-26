Directory: "./../skillmodule/skills"  
Module: SkillModule

A skill may level up to a certain point, the "LEVEL" variable is available everywhere. The damage mechanic, the entity attribute effect, the damage modification mechanic and any sort of variable can read up on the level. However beware that the level of a skill is fixed to when it has been acquired, you cannot change the level of a skill while you are using it.

## Level Attribute

A skill may gain additional levels based on its tags. The tags are specified in the `level-scaling`, and automatically include the id of the skill as an extra tag. You can make it so that your items add a support/secondary skill, so every skill socketed on that item would receive some extra levels.

| Attribute | Type | Description |
|-|-|-|
| LOCAL_SKILL_LEVEL_\<TAG> | skill attribute | an attribute within the skill, scales based on tags |
| GLOBAL_SKILL_LEVEL_\<TAG> | entity attribute | an attribute on the entity, scales based on tags |

## Level-Up (Killing)

Killing mobs can grant skill experience, as specified in [[EntityModule: Creatures]] - when you gather sufficient experience the player will be shown a chat notification where they can hit the level up icon again. Note that the skill will only be levelling up if it actually has the experience to do so, hitting the icon again will not bring any benefits.

## Level-Up (Material)

The upgrade materials listed in [[ItemModule: Materials]] include one which can grant experience to a skill. You just need to apply it on an item by clicking on the itemized skill with it.

## Configuring Levelling

The skill module has a `default-level-configuration` option specifiying the experience needed for a skill to level up, however if you want a skill itself to have a different experience curve you may define `level-configuration` - where every entry is for one level.