Directory: "./../itemmodule", "./../offhandmodule.yml"  
Module: ItemModule, OffhandModule

# Usage of Traps

Using a trap opens up the ability to place a trap to use your spells in your place. The skill socketed on the trap will be used by it once the trap is triggered. Beware that traps using skills are like you using the skills, hence you are receiving the aggro of a trap.

Traps are worked of in the sequence they are triggered, at an interval of 0.1 seconds. Traps are triggered if a target is close enough, the placing player has hit the crouching button or they ran out of duration.

This is meant to be used in context with the `trap` trigger, beware that damage inflicted by the trap trigger will add "TRAP" as a damage type. 

| Keyword | Type | Description |
|-|-|-|
| skill-modifiers | attribute list | extra modifiers for skill parameters, does not access entity |

Beneath is an example for a totem that you can add to your offhand, it gives players a rather massive crit chance.

# Example for Traps

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

