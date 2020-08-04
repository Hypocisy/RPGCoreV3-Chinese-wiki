Directory: "./../Passives"  
Module: Passives, Levels, Skills

When creating a passive tree, you should split your work into three steps. While you can fully process it with just config files, the workflow described below is the optimal one once you get a grip on it. It is **not** possible to fully create a passive tree within the game.

Beware that creating a passive tree is extremely time intensive.

**Important:** Passive tree files are saved every time the server shuts down. Do NOT modify the files while the server is running, otherwise your changes to the files will be lost without any way of recovering them.

## Step 1: preparing the files

1. Shut down your server
2. Create passive point rewards, matching the category, in the LevelModule configuration
3. Create an extra section in the 'passive-tree-register' of the PassiveTreeModule configuration
4. Add the passive tree in the 'advancement-options' to give players a way to unlock the tree
5. Start up your server again

| Option | Type | Description |
|-|-|-|
| displayname | string | name of the passive tree added |
| icon | material | material:model item used as the icon |
| anchoring | string | passive point type, player can only have one tree of one type |
| description | string list | details of this tree |
| axis-lock-x | boolean | prevent scrolling on x axis |
| axis-lock-z | boolean | prevent scrolling on z axis |
| free-form-tree | boolean | skip connectivity check and skip origin selection |
| icon-override | string | icon used in character screen |
| icon-priority | integer | use icon with highest priority on character screen |

## Step 2: creating a layout

Create a prototype layout by creating a number of nodes and just copying them, there are instructions to the top-left on which keybinds you should utilize. Just copy-paste the same node over and over again, you only need to know what purpose the node will serve. 

I suggest you avoid defining explicit uses for the node using just "speciality type a", "speciality type b" etc so you can group things up afterwards.

Important: **Make sure to shut down your server after finishing prototyping**

[Video on how to quickly proto-type upcoming]

## Step 3: modifying configurations

After you got your prototype, you should get working to modify the configuration file. It is recommended that you create all the node types in one go, and then just apply a copy-paste operation. There are the following options when you deal with a passive tree

### Creating: Combat modifiers

Modifies the combat interaction directly, note that while this shares the attribute notation do not confuse it as an attribute modifier. Effects can use TREE_INVESTMENT as a variable.

| Option | Type | Description |
|-|-|-|
| wanted-types | string list | contain one type to trigger |
| as-attacker | boolean | attacker or defender role to affect |
| effects | attribute list | modifiers that are added to the **combat** interaction, notation written like attributes |
| custom-formatting | section | when the data is more complex that the auto generated description can document, write the custom formatting in this section. |

```yml
    combat:
      wanted-types:
      - TRAP
      as-attacker: true
      effects:
      - ADD 15% TO DAMAGE_FIRE
```

### Creating: Attribute modifiers

Modifies the attributes of the player directly.

| Option | Type | Description |
|-|-|-|
| effects | attribute list | modifiers affecting the entity. |
| custom-formatting | section | when the data is more complex that the auto generated description can document, write the custom formatting in this section. |

```yml
    attribute:
      effects:
      - ADD 10 TO SHIELD_AMOUNT
      - ADD 10% TO SHIELD_AMOUNT
```

### Creating: Gear tags

Should you have equipment restrictions setup, you can grant access to certain items from here.

| Option | Type | Description |
|-|-|-|
| gear-tags | string list | list of tags that get unlocked - use readable names for your tags! |

```yml
    gear:
      gear-tags: [Heavy Armor, Plate Armor]
```

### Creating: Minion Attribute, Minion Combat

Behaves identical to the attribute and combat option, just applying it on minions summoned. There is **no** difference, no additional documentation is necessary as the only difference is who will receive the effect.

```yml
    minion-attribute:
      effects:
      - ADD 10 TO SHIELD_AMOUNT
    minion-combat:
      wanted-types:
      - ATTACK
      as-attacker: true
      effects:
      - ADD 13% TO DAMAGE_PHYSICAL
```

### Creating: Skill Option

This will grant a player access to a certain skill, this can either be a pre-existing skill OR create a local skill for this node & grant access to that. 

```yml
    # grant access to a pre-existing skill
    skill-existing:
      skills:
      # grants access to the primary fireball behaviour at lv13. Highest levelled skill is given
      - "FIREBALL:AUTO:13"
    # create a local skill and grant access to it
    skill-local:
      # if the id is the same, we recycle the skill. Still only 1 copy is gained
      id: UNBREAKABLE
      behaviours:
        UNBREAKABLE:
          # not necessary, but a good practice
          id: UNBREAKABLE
          # acquire only primary behaviour
          primary: true
          # skill procs on taking damage
          trigger: take-damage{finished=false}
          # cannot passively dodge/block, every 2s take no crit damage.
          actions:
          - modify-damage{setup=REMOVE 100%% OF BLOCK_CHANCE}@self
          - modify-damage{setup=REMOVE 100%% OF DODGE_CHANCE}@self
          - modify-damage{cooldown=40;setup=REMOVE 100%% OF CRIT_DAMAGE}@self
```