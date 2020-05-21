Directory: "./../entitymodule/creatures"
Module: EntityModule

Only monsters that were created by rpgcore will be affected by it, do not utilize a third party mob plugin.

# Configuration

| Option | Type | Description | Defaults |
|-|-|-|-|
| | | | |
| leash-range | integer | teleport to spawnpoint after exceeding distance | -1 |
| experience | integer | player experience granted when slain | 0 |
| skill-experience | integer | skill experience granted when slain | 0 |
| action.behaviour | behaviour | aggresive (seek enemy) or neutral (wait to be attacked) | / |
| action.style | style | melee, leap melee, leap melee dual, archer or caster | / |
| display.type | [type](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/entity/EntityType.html) | monster base type | / |
| display.name | string | displayname of the monster | / |
| display.disguise | [disguise configuration](https://github.com/Blutkrone/RPGCoreV3/wiki/EntityModule:-Creatures#disguises) | disguise of the monster | / |
| equipment | item list | either a material or an rpgcore item, lead with [slot](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/inventory/EquipmentSlot.html) | / |
| loot-table | [loot table](https://github.com/Blutkrone/RPGCoreV3/wiki/EntityModule%3A-Looting) | looting configuration of mob | / |
| attributes | attribute list | a list of attribute modifiers applied | / |
| skills | [skill configuration](https://github.com/Blutkrone/RPGCoreV3/wiki/EntityModule:-Creatures#skills) | either a custom skill or some linked skills | / |

# Disguises

Prequisite (1): https://www.spigotmc.org/resources/libs-disguises.32453/  
Prequisite (2): https://www.spigotmc.org/resources/rpgcore-libsdisguises-bridge-v1-13-v1-15.72994/  
Recommended: https://mineskin.org/

| Option | Type | Description | Defaults |
|-|-|-|-|
| | | | |
| display.disguise.raw | string | disguise string within the libsdisguise specifications | / |
| player | string | when using a player, define a name here | / |
| signature | base64 string | when using a player, define a skin signature here | / |
| encoded | base64 string | when using a player, define a skin encoding here | / |

# Skills

You can define a custom skill within the skill configuration of a mob, allowing you to generate a unique behaviour specific to this mob.

```
  skills:
    # Instead of using the skills defined by the skill module, we got a unique
    #  mechanic that affects this mob
    CRACK_SHOOTER_RAMP_UP:
      # make sure that the skill id is unique
      id: CRACK_SHOOTER_RAMP_UP
      # prequisite: https://www.spigotmc.org/resources/69476/
      depends:
      - "com.blutkrone.rpgcorearrows.RPGCoreArchery"
      behaviours:
        # This is gained when we pierce a mob, buffing our damage
        CRACKSHOOTER_PIERCE:
          id: CRACKSHOOTER_PIERCE
          name: "&aCrackshooter"
          # Any hitting damage will be affected 
          trigger: deal-damage{finished=false;wanted-types=HIT}
          actions:
          # 10% Crit Chance for each enemy we pierced recently
          - "modify-damage{setup=[ADD CRACKSHOOTER_PIERCE*10%% TO CRIT_CHANCE]}@self"
          # 10% Crit Multi for each enemy we pierced recently
          - "modify-damage{setup=[ADD CRACKSHOOTER_PIERCE/10 TO CRIT_DAMAGE]}@self"
        # The crackshooter gains damage if it pierced someone recently
        CRACK_SHOOTER_RAMP_UP:
          primary: true
          # the rpgcore archer module adds a trigger for this
          trigger: arrowpierced
          # Make sure we pierced a hostile target
          conditions:
          - "target"
          - "hostile"
          actions:
          # Gain crackshooter effect, stacks 20 times and refreshes to 10 seconds.
          - "attachment{behaviours=CRACKSHOOTER_PIERCE;stacks=20;duration=200}@self"
```

You can recycle skills from the skill module. These are the same ones as players will have access to. When you define a skill like this, the loot table can end up dropping it - giving players access to the level 1 version of the skill.

```yaml
  skills:
    SKILL_GROUP_1:
    # Grant Lv10 double strike, affected by global skill level modifiers.
    - "DOUBLE_STRIKE:10"
    # Link double strike with a Lv10 "Added fire damage with hits" support. 
    - "SUPPORT_FIRE_DAMAGE_WITH_HITS:10"
```