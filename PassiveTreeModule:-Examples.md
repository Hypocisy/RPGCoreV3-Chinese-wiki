Directory: "./../passivetreemodule"  
Module: PassiveTreeModule, LevelModule, SkillModule

Owing the challenge of creating a proper passive tree, beneath you can find some selective examples serving specific purposes. It serves both as a repository, and as a reference for you to create your own assets.

## Investable nodes

An investable node refers to a node where you can put multiple points into. The suggested usage is either in a free-form tree (no entry point, no connectivity verification) - quite helpful if you don't want to create a tree with the same node a thousand times over. 

```yml
41b1c8be-7709-46b1-8f1f-2ba17ad0dd45:
  uuidpos: -1 -2
  x: -1
  z: -2
  icon:
    icon-assigned: DIAMOND_HOE:2
    icon-assignable: DIAMOND_HOE:2
    icon-unreachable: DIAMOND_HOE:2
    displayname: Fire Resistance
    description:
    - '&aYour default maximum fire resistance is 75%'
    - '&aPenetration is applied on capped resistance'
    - '&aYour uncapped resistance is affected by curses'
    - '&aResistance and penetration only affects hit damage.'
    - '&7+1% to fire Resistance for each point invested'
    - '&7+1% to maximum fesistance per 25 points invested'
    - '&7+8% to fire resistance penetration with 100 points'
  # up to 100 points can be invested into this
  investment-limit: 100
  options:
    attribute:
      effects:
      # +1% fire resistance per point invested
      - ADD 0.01*TREE_INVESTMENT TO RESISTANCE_FIRE
      # when you have all points invested, grants some fire penetration
      - ADD 0.08*MAX(0,TREE_INVESTMENT-100) TO PENETRATION_FIRE
      # for every 25 points, we grant 1% maximum fire resistance
      - ADD 0.01*FLOOR(TREE_INVESTMENT/25) TO MAXIMUM_RESISTANCE_FIRE
```

# Generic pathing nodes

A generic pathing node refers to a node where you only put one point into, but will have lots of. Useful if you want a large passive tree where players need careful pathing for. Avoid having complex logic implemented into these (ex: avoid skills being pathing nodes, avoid having some sort of formula in them.)

```yml
30578968-f547-42d4-a34a-a72d51b1645d:
  uuidpos: 1 0
  x: 1
  z: 0
  icon:
    icon-assigned: LEATHER_CHESTPLATE:2:806000
    icon-assignable: LEATHER_CHESTPLATE:2:806000
    icon-unreachable: LEATHER_CHESTPLATE:2:806000
    displayname: Stamina
    description: []
  options:
    # we gain 10 stamina and 1% physical resistance per point
    attribute:
      effects:
      - ADD 10 TO STAMINA
      - ADD 0.01 TO RESISTANCE_PHYSICAL
```

# Powerful unique nodes

A passive tree gets a lot more interesting if there are some very strong passive nodes, potentially enabling a certain playstyle. Optimally, players should not be able to pick up every keynode so that there actually is some meaning to having multiple of them.

```yml
7e30f3c8-7856-4691-8932-3f563c7bb81f:
  uuidpos: 4 2
  x: 4
  z: 2
  icon:
    icon-assigned: LEATHER_CHESTPLATE:5:806000
    icon-assignable: LEATHER_CHESTPLATE:5:806000
    icon-unreachable: LEATHER_CHESTPLATE:5:806000
    displayname: 'Keynode: Unbreakable'
    description:
    - You cannot block or dodge any type of damage
    - No more then once every 2 seconds, take no extra damage from crits
    # Assign a specific description to the node
    forced-description: You have 'Unbreakable'
    # make sure that the node cannot be owned twice
    global-unique: unbreakable
    # make sure that the node cannot be owned twice
    local-unique: unbreakable
  options:
    # as the logic is a bit more complex, we should use a skill to process it
    skills:
      id: UNBREAKABLE
      behaviours:
        UNBREAKABLE:
          id: UNBREAKABLE
          primary: true
          # we process our logic when we take damage
          trigger: take-damage{finished=false}
          actions:
          # make sure that we cannot dodge or block
          - modify-damage{setup=REMOVE 100%% OF BLOCK_CHANCE}@self
          - modify-damage{setup=REMOVE 100%% OF DODGE_CHANCE}@self
          # with a cooldown of 40 ticks, makes sure that there is no crit damage.
          - modify-damage{cooldown=40;setup=REMOVE 100%% OF CRIT_DAMAGE}@self
```