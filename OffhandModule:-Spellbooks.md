Directory: "./../itemmodule", "./../offhandmodule.yml"  
Module: ItemModule, OffhandModule

# Usage of Spellbooks

Using a spell book opens up the ability to cast spells. Using a permutation of actions (Left click, Right click, Drop Item, Switch item) will allow you to selectively cast a certain spell. Note that "spells" are referring to skills which are setup to be casted with this.

This is meant to be used in context with the `cast` trigger, beware that damage inflicted by the cast trigger will add "SELF_CAST" as a damage type.

| Keyword | Type | Description |
|-|-|-|
| skill-modifiers | attribute list | extra modifiers for skill parameters, does not access entity |

# Example for Spellbooks

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