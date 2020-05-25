Directory: "./../itemmodule", "./../offhandmodule.yml"  
Module: ItemModule, OffhandModule

# Usage of Shields 

Using a shield opens up "Blocking Power", the resource is recovered when your shield is lowered and consumed when your shield is raised. When you exhaust your blocking power, your shield will be put on a cooldown. The blocking power will absorb all damage, so long you have sufficient amounts of it.

Blocking from the "BLOCK_CHANCE" attribute and blocking from raising your shield will both be adding the "BLOCKED" to the damage interactions you have suffered.

| Keyword | Type | Description |
|-|-|-|
| shield-absorption | integer | flat amount of blocking power to receive |
| shield-absorption-percent | percentage | relative amount of blocking power to health and shield |
| shield-recovery | percentage | percentage of blocking power to recover per second while shield is lowered |
| shield-decay | percentage | percentage of blocking power to lose per second while shield is raised |
| shield-targets | damage type list | a specific list of damage types that can be blocked |

# Example for Shields

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