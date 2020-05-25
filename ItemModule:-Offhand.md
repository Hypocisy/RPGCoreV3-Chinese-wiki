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

Beneath is an example for a shield that you can add to your offhand, it absorbs any kind of damage and grants a passive chance to absorb any kind of damage.

```yml
BULWARK_SHIELD:
  id: BULWARK_SHIELD
  name: "Bulwark Shield"
  lore:
  - "Equip to your offhand to enable shield blocking"
  - "Absorb a certain amount of damage while shield is raised"
  - "Blocking capacity is recovered while shield is lowered"
  - "When exhausting blocking capacity, a cooldown is applied"
  - "Gain 30% of your maximum shield as blocking capacity"
  - "Gain 30% of your maximum health as blocking capacity"
  - "While shield is raised, -8% blocking capacity per second"
  - "While shield is lowered, +6% blocking capacity per second"
  material: SHIELD
  seed: true
  unbound-modifiers:
  - ADD RANGE(0.27,0.35,0.01) TO BLOCK_CHANCE
  custom-tags:
    affixing-pool: WEAPON
    default-link-fortune: 10
    offhand-type: SHIELD
    display-binding: OFFHAND
    shield-absorption: 0
    shield-absorption-percent: 30%
    shield-targets: []
    shield-recovery: 6%
    shield-decay: 8%
```

## Offhand Tool: Spellbook

Using a spell book opens up the ability to cast spells. Using a permutation of actions (Left click, Right click, Drop Item, Switch item) will allow you to selectively cast a certain spell. Note that "spells" are referring to skills which are setup to be casted with this.

This is meant to be used in context with the `cast` trigger, beware that damage inflicted by the cast trigger will add "SELF_CAST" as a damage type.

| Keyword | Type | Description |
|-|-|-|
| skill-modifiers | attribute list | extra modifiers for skill parameters, does not access entity |

Beneath is an example for a spellbook that you can add to your offhand, should a player use that spellbook any spell of theirs will have some additional cast time reduction to it. Beware that you need mana to cast spells!

```yml
VOIDLIGHT_SPELLBOOK:
  id: VOIDLIGHT_SPELLBOOK
  name: "Voidlight Spellbook"
  lore:
  - "Equip to your offhand to enable spell casting"
  - "Use R-L-Q-F combinations to cast a skill."
  - "The spellbook itself will not give you skills."
  - "Your skill specifies the casting combination."
  material: ENCHANTED_BOOK
  seed: true
  unbound-modifiers:
  - "ADD RANGE(25,75) TO MANA_AMOUNT"
  - "REMOVE RANGE(15,25)% OF SKILL_CAST_TIME:SPELL"
  custom-tags:
    affixing-pool: WEAPON
    display-binding: OFFHAND
    default-link-fortune: 10
    offhand-type: TOME
    skill-modifiers: []
```

## Offhand Tool: Totem

Using a totem opens up the ability to summon a totem to use your spells in your place. The skill socketed on the totem will be used by it, until it runs out of summoning time. Beware that totems using skills are like you using the skills, hence you are receiving the aggro of a totem.

This is meant to be used in context with the `totem` trigger, beware that damage inflicted by the totem trigger will add "TOTEM" as a damage type. Players hitting the totem in melee will cause it to run out of summoning time even faster.

| Keyword | Type | Description |
|-|-|-|
| skill-modifiers | attribute list | extra modifiers for skill parameters, does not access entity |

Beneath is an example for a totem that you can add to your offhand, it gives players access to a huge amount of flat mana.

```yml
ANCESTRAL_TOTEM:
  id: ANCESTRAL_TOTEM
  name: "Ancestral Totem"
  lore:
  - "Equip to your offhand to enable totem placement"
  - "You need to equip a spell skill on this item."
  - "Some skills may not support being cast by a totem."
  - "Hit a block to place a totem that will use the skill."
  - "Multiple totems can be placed, limited by the skill."
  - "Totem mana cost applies when they are placed."
  - "Totems do not draw aggro from mobs, but are temporary."
  - "Players hitting totems will make it unsummon faster."
  material: DIAMOND_HOE
  custom-model: 30
  seed: true
  unbound-modifiers:
  - ADD RANGE(150,200) TO MANA_AMOUNT
  custom-tags:
    affixing-pool: WEAPON
    default-link-fortune: 10
    offhand-type: TOTEM
    display-binding: OFFHAND
    skill-modifiers: []
```

## Offhand Tool: Trap

Using a trap opens up the ability to place a trap to use your spells in your place. The skill socketed on the trap will be used by it once the trap is triggered. Beware that traps using skills are like you using the skills, hence you are receiving the aggro of a trap.

Traps are worked of in the sequence they are triggered, at an interval of 0.1 seconds. Traps are triggered if a target is close enough, the placing player has hit the crouching button or they ran out of duration.

This is meant to be used in context with the `trap` trigger, beware that damage inflicted by the trap trigger will add "TRAP" as a damage type. 

| Keyword | Type | Description |
|-|-|-|
| skill-modifiers | attribute list | extra modifiers for skill parameters, does not access entity |

Beneath is an example for a totem that you can add to your offhand, it gives players a rather massive crit chance.

```yml
MECHANICAL_TRAP:
  id: MECHANICAL_TRAP
  name: "Mechanical Trap"
  lore:
  - "Equip to your offhand to enable trap placement"
  - "You need to equip a trap skill on this item."
  - "Hit a block to place a trap that can be triggered."
  - "Multiple traps can be placed, limited by the skill."
  - "Trap cooldown applies when they are triggered."
  - "Trap mana cost applies after they are placed."
  - "Traps are triggered under following conditions"
  - "(1) Trigger all placed traps at once by crouching."
  - "(2) Trigger a placed trap when a target is close to it."
  - "(3) Trigger a placed trap when it runs out of time."
  material: DIAMOND_HOE
  custom-model: 67
  seed: true
  unbound-modifiers:
  - ADD RANGE(50,75) TO MANA_AMOUNT
  - ADD 0.30 TO CRIT_CHANCE_HIT
  custom-tags:
    affixing-pool: WEAPON
    display-binding: OFFHAND
    default-link-fortune: 10
    offhand-type: TRAP
    skill-modifiers: []
```