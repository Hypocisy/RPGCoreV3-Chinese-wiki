Directory: "./../itemmodule/items"  
Module: ItemModule, SkillModule

Consumable items are a special case, it behaves differently then other behaviours as to allow it integrating into the skill system while still retaining the "consumable" aspect of it. By design, a consumable is meant to used attach a behaviour to the player for the duration of its buff effect or grant an instant effect to them.

You may need to read additional articles on the respective skill module sections to make more complex things with the module, but the two examples below should be sufficient to give you an idea of what you can do. There is no restriction to what you can do with the consumable, just remember that the 'consumable' trigger only is meant to be an entry point.

# Skill Trigger 'consume'

When a behaviour has a trigger like this it should **not** be marked as a primary or secondary behaviour. It will only be present for the instant of "consuming" it (right click while holding the item)

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | string | | consume | yes | no |
| noconsume | ticks | ticks cooldown applied to the material | 20 | no | yes |
| blocking | materials | list of materials that cannot be consumed | | no | no |

# Creating a consumable (Buff item)

The following is a stackable consumable, that will increase your strength for a certain duration.

```yml
POTION_OF_STRENGTH:
  id: POTION_OF_STRENGTH
  material: DIAMOND_HOE
  custom-model: 201
  custom-tags:
    overstacking: 10
  lore:
  - "&bRight click to consume, the effect lasts 15 minutes."
  - "&bThe effect can stack up to 3 times"
  - "&aGrants you 5% increased total strength."
  name: "Potion of strength"
  seed: false
  rarity: UNCOMMON
  consumable:
    # make sure the Id is unique in the skill system
    id: POTION_OF_STRENGTH
    # setup the behaviours meant for the consumable
    behaviours:
      # this will be instantly added, handled removed should you "consume" the item
      ACCEPT_CONSUMABLE:
        # procs whenever we consume an item of this type, you can just copy-paste
        # this for your own consumables and adjust stacking/duration
        trigger: consume
        actions:
        # grants "POTION_ATTACHMENT" to yourself, lasting 18.000 ticks and stacking up to 3 times
        - "attachment{stacks=3;duration=18000;individual=false;behaviours=POTION_ATTACHMENT}@self"
      # the actual effect acquired when consuming the item
      POTION_ATTACHMENT:
        # ensure that the Id is unique
        id: POTION_OF_STRENGTH
        # utilized to display the effect
        name: "&aPotion of Strength"
        # the effect procs every 20 ticks
        trigger: timer{interval=20}
        # the effect just spawns a bunch of particles around the owner
        actions:
        - "particle{class=SINGLE;points=3;particle=SPELL_MOB;color=00ff00;random=1}@self"
        - "particle{class=SINGLE;points=3;particle=REDSTONE;color=00ff00;random=1}@self"
        # while we have this behaviour, we gain 5/10/15% increased total strength        
        attribute-effect:
          cluster: BUFF
          effects:
          - "ADD 5*STACKS(POTION_OF_STRENGTH)% TO STRENGTH"
```

# Creating a consumable (Recovery item)

The following is a consumable that will instantly recover a fraction of your health and energy shield, while also granting you a short buff that will recover some more resources over a certain period. The instant recovery has a cooldown so it cannot be abused.

```yml
POTION_OF_RECOVERY:
  id: POTION_OF_RECOVERY
  material: DIAMOND_HOE
  custom-model: 212
  custom-tags:
    overstacking: 10
  lore:
  - "&bRight click to consume, the effect does not stack."
  - "&bThe instant recovery effect has a cooldown of 5 seconds"
  - "&bThe instant recovery cooldown is shared between potions"
  - "&aGrants you 2% health and shield regeneration for 5 seconds"
  - "&aInstantly recovers 10% of your health and shield value"
  name: "Potion of Recovery"
  seed: false
  rarity: UNCOMMON
  consumable:
    id: POTION_OF_RECOVERY
    name: "Potion of Recovery"
    lore: []
    variable-register: {}
    behaviours:
      ACCEPT_CONSUMABLE:
        trigger: consume
        actions:
        # for 5 seconds, you will regenerate 2% health and shield per second
        - "attachment{duration=100;individual=false;behaviours=POTION_ATTACHMENT}@self"
        # if last usage is 5 seconds ago, recover 10% of your total health
        - "resource{cooldown=100;cooldown-id=RECOVERY_POTION_HEALTH;cooldownid=;percent=true;set=false;amount=0.10;target=SHIELD}@self"
        # if last usage is 5 seconds ago, recover 10% of your total health
        - "resource{cooldown=100;cooldown-id=RECOVERY_POTION_SHIELD;percent=true;set=false;amount=0.10;target=HEALTH}@self"
      # A behaviour that while attached grants a regeneration effect
      POTION_ATTACHMENT:
        id: POTION_OF_RECOVERY
        name: "&aPotion of Recovery"
        # every 20 ticks spawn some particles to indicate that the potion is active
        trigger: timer{interval=20}
        actions:
        - "particle{class=SINGLE;points=3;particle=SPELL_MOB;color=00ff00;random=1}@self"
        - "particle{class=SINGLE;points=3;particle=REDSTONE;color=00ff00;random=1}@self"
        # while attached, +2% to percentage regeneration attribute of the player.
        attribute-effect:
          cluster: BUFF
          effects:
          - "ADD 0.02 TO HEALTH_PERCENT"
          - "ADD 0.02 TO SHIELD_PERCENT"
```