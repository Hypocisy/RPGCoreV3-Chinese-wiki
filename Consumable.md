Triggered when "consuming" an item, beware that this **only** meant to be used together with the item system to create consumables. Do not use this in any other context.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | string | | consume | yes | no |
| noconsume | integer | ticks to block all relevant ids | 0 | no | yes |
| blocking | string list | consumable skill ids to block | empty | no | no |

## An example use-case of a consumable item

This refers to the configuration of an item, specifically a potion that will recover health.

```YML
POTION_OF_RECOVERY:
  # this is the item id
  id: POTION_OF_RECOVERY
  # material and custom texture
  material: DIAMOND_HOE
  custom-model: 212
  # permit to stack up diamond hoes
  custom-tags:
    overstacking: 10
  # display name of the item
  name: "Potion of Recovery"
  # description of the item
  lore:
  - "&bRight click to consume, the effect does not stack."
  - "&aInstantly recovers 10% of your maximum health value"
  - "&aYou cannot consume this potion within 3 seconds."
  # we cannot stack seeded items
  seed: false
  # force a rarity on the item
  rarity: UNCOMMON
  # a skill configuration for a consumable
  consumable:
    # this is the skill id, which blocking scales off.
    id: SKILL_ID_POTION_OF_RECOVERY
    # not necessary, but good practice
    name: "Potion of Recovery"
    lore: []
    variable-register: {}
    # setup behaviours to execute
    behaviours:
      # this behaviour is going to be called when consuming the item
      ACCEPT_CONSUMABLE:
        # prevents re-use within 3 seconds. Called upon consuming.
        trigger: consume{noconsume=60;blocking=SKILL_ID_POTION_OF_RECOVERY}
        actions:
        # instant recovery effect for your health
        - "resource{percent=true;set=false;amount=0.10;target=HEALTH}@self"
```