Directory: "./../EquipmentRestrictionModule.yml"  
Module: EquipmentRestrictionModule

Serves to restrict players from equipping certain items. Note that even if some sort of a exploit is found to equip the item, the player still is not going to receive the effects of it. Only players will be checked for equipment conditions.

# Module configuration

| Option | Type | Description |
|-|-|-|
| cannot-equip-message | string | warn the player about not being able to equip the item |
| restricted-slots-by-chest-name | section | additional inventory positions to scan |

# Item configuration 

Note that an admin will always bypass this check, the following are all expected as some sort of NBT tags.

| Option | Type | Description |
|-|-|-|
| requirements.item-tags | string list | a listing of item tags required to equip the item |
| requirements.attribute | attribute map | attribute mapped to the minimum amount we need to exceed |
| requirements.minimum-level | integer | the minimum level of the player |
| requirements.maximum-level | integer | the maximum level of the player |

Beneath, an example for an equipment piece that can be equipped between Lv50 to 110 should you have the "Heavy Armor" tag (only gained from the passive tree) and a minimum of 300 stamina and 150 strength.

```yml
TEMPLAR_HELMET:
  id: TEMPLAR_HELMET
  name: "Templar Helmet"
  material: LEATHER_HELMET
  seed: true
  implicits:
  - ADD RANGE(400,500) TO STAMINA
  - ADD 0.20 TO RESISTANCE_PHYSICAL
  - ADD 5% TO HEALTH_AMOUNT
  leather-color: "FFFF00"
  custom-tags:
    affixing-pool: ARMOR
    set-effect: TEMPLAR 
    default-link-fortune: 1
    default-affixes: 1
    default-sockets: 1
    default-upgrade-cap: 6
    requirements:
      item-tags: [Heavy Armor]
      attribute:
        STRENGTH: 150
        STAMINA: 300
      minimum-level: 50
      maximum-level: 110
    
```