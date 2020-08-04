Directory: "./../items", "./../offhand.yml"  
Module: Items, Offhand

# Usage of Totems

Using a totem opens up the ability to summon a totem to use your spells in your place. The skill socketed on the totem will be used by it, until it runs out of summoning time. Beware that totems using skills are like you using the skills, hence you are receiving the aggro of a totem.

This is meant to be used in context with the `totem` trigger, beware that damage inflicted by the totem trigger will add "TOTEM" as a damage type. Players hitting the totem in melee will cause it to run out of summoning time even faster.

| Keyword | Type | Description |
|-|-|-|
| skill-modifiers | attribute list | extra modifiers for skill parameters, does not access entity |

# Example for Totems

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

