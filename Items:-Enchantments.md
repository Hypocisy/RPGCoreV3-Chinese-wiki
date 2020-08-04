Directory: "./../Items/items"  
Module: Items, Skills

Enchantments simply are skills that can be persistently added to an item, unlike normal skills you cannot socket/unsocket them.

# Setup an enchantment (./../Items/enchants)

An enchantment is expected to be a skill, with a special section added to it. Everything applying to [[Skills]] also applies to enchantments. **Note that this includes the restriction that a primary behaviour cannot be held multiple times!**

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| enchant.namespace | string | cannot roll enchants who have the same namespace | / | yes | no |
| enchant.weight | decimal | chance to roll this enchantment option | / | yes | yes |
| enchant.target | string list | enchantment target items, item has to own tag | / | yes | no |
| enchant.max-level | integer | a random level that can be rolled for the enchantment | / | yes | no |

The following is an enchantment skill configuration

```yml
ENCHANT_OVERKILL_REGENERATION:
  id: ENCHANT_OVERKILL_REGENERATION
  name: "&aOverkill Recovery"
  enchant:
    namespace: ENCHANT_OVERKILL_REGENERATION
    weight: 1.0
    target: [WEAPON]
    max-level: 5
  behaviours:
    PROC_SUPPORT_EFFECT_DAMAGE:
      primary: true
      trigger: kill{cooldown=60;cooldown-id=ENCHANT_OVERKILL_REGENERATION}
      actions:
      - "resource{interval=20;repeat=3;target=HEALTH;set=false;percent=false;amount=OVERKILL_AMOUNT*0.10*LEVEL}@self"
```

# Acquiring enchantments

You need to use enchantment materials to apply them to items, `enchantment-fortune` being the relevant option. The enchantments are based off the target, not the material. Cannot consume material if no enchantments can be rolled.

```yml
RANDOM_ENCHANTMENT_SCROLL:
  breakdown:
    '50': 10
  dropable:
    weighting: 2.0
    drop-level: 100
    tagging: [MATERIAL, MATERIAL_T3]
  id: RANDOM_ENCHANTMENT_SCROLL
  name: "Random Enchantment Scroll"
  lore:
  - "Use on an item to enchant it, should it have open slots"
  - "Similar enchantments cannot be rolled multiple times"
  - "Different items can roll different enchantments"
  - "&a{SUCCESS_CHANCE}%&7 chance to enchant item"
  material: PAPER
  rarity: LEGENDARY
  seed: false
  super-stash-stacking: 9999
  browser-group: 
    icon: DIAMOND_HOE:62
    displayname: "Upgrade Materials"
  custom-tags:
    success-chance: 100%
    enchantment-fortune: 50%
```