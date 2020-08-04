Directory: "./../Skills"  
Module: Skills

Status effects are a necessity for every RPG, an effect cluster refers to what allows you to scale them. By default, there are only two clusters available. One for buff effects and one for curse effects. You can scale entity attribute effects and combat attribute effects, both applying as a magnitude scalar (defaults to 1.0, applied as a multiplier atop the final result.)

## Configuring Clusters

A cluster refers to something which scales the effects present on an entity.

| Option | Type | Description |
|-|-|-|
| effect-cluster.flush-effect-interval | integer | updating interval for entity attributes |
| clusters-to-register.id | string | id of the cluster |
| clusters-to-register.default-maixmum | integer | relative to caster, how many effects can be stacked on a target |
| clusters-to-register.effectiveness-dealt | string | entity attribute for applied magntitude |
| clusters-to-register.effectiveness-taken | string | entity attribute for received magnitude |

## Entity Attribute Effect

Beneath is a setup for a skill which reduces the time necessary for a player to cast a spell with a spellbook. It is fixed at 18% unless the caster or recipient their cluster attribute scales it.

Note that these two attributes are defined in the default configuration, you may use other namespaces for your own.

```yml
  behaviours:
    EFFECT_NOTIFICATION_WRAPPER:
      id: BLESSING_CAST_TIME_UP
      name: "&aSpell Onslaught"
      trigger: timer{interval=20}
      actions:
      - "particle{class=SINGLE;points=3;particle=SPELL_MOB;color=00ff00;random=1}@self"
      - "particle{class=SINGLE;points=3;particle=REDSTONE;color=00ff00;random=1}@self"
      attribute-effect:
        cluster: BLESSING
        effects:
        - "REMOVE 18% OF SKILL_CAST_TIME"
    CAST_VIA_TOME:
      primary: true
      mana: {flat: 10}
      trigger: cast{casttime=20;cooldown-id=Enhance Skill Cast Time;channel-cooldown=20;instruction=RLR}
      actions:
      - "attachment{stacks=1;duration=100;individual=false;behaviours=EFFECT_NOTIFICATION_WRAPPER}@self"
```

## Combat Attribute Effect

Beneath is a setup for a skill which causes a player to take more crit damage when struck. It is fixed at 18% unless the caster or recipient their cluster attribute scales it.

Make sure you have the attribute effect setup even if you do not use it, otherwise the caster will not check if the target can still apply another effect. 

```yml
  behaviours:
    EFFECT_NOTIFICATION_WRAPPER:
      id: CURSE_CRIT_DAMAGE
      name: "&aCrit Damage Curse"
      trigger: damage-taken{finished=false}
      actions:
      - "modify-damage{setup=ADD 0.18 TO CRIT_DAMAGE;cluster=CURSE}@self"
      attribute-effect:
        cluster: CURSE
        effects: []
    CAST_VIA_TOME:
      primary: true
      mana: {flat: 15}
      trigger: cast{casttime=20;cooldown-id=Crit Damage Curse;channel-cooldown=20;instruction=RLR}
      actions:
      - "attachment{stacks=1;duration=100;individual=false;behaviours=EFFECT_NOTIFICATION_WRAPPER}@self"
```

