Directory: "./../Entities"  
Module: Entities

Only monsters that were created by rpgcore will be affected by it, do not utilize a third party mob plugin. 

RPGCore mobs also are affected by potion effects. Invisibility will cause them to lose track of their target and blindness may cause them to fail with their auto attacks.

# Configuration

| Option | Type | Description | Defaults |
|-|-|-|-|
| | | | |
| stationary | boolean | will not move from spawnpoint | false |
| hostile-tags| tag list | entity tags we are hostile towards | |
| friendly-tags | tag list | entity tags we are friendly towards | |
| entity-tags | tag list | entity tags for ourself | |
| leash-range | integer | teleport to spawnpoint after exceeding distance | |
| experience | integer | player experience granted when slain | |
| skill-experience | integer | skill experience granted when slain | |
| action.behaviour | behaviour | aggresive (seek enemy) or neutral (wait to be attacked) | required |
| action.style | style | melee, leap melee, leap melee dual, archer or caster | required |
| display.type | [type](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/entity/EntityType.html) | monster base type | required |
| display.name | string | displayname of the monster | required |
| display.disguise | [section](https://github.com/Blutkrone/RPGCoreV3/wiki/EntityModule:-Creatures#disguises) | disguise of the monster | |
| equipment | item list | either a material or an rpgcore item, lead with [slot](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/inventory/EquipmentSlot.html) | |
| loot-table | [loot table](https://github.com/Blutkrone/RPGCoreV3/wiki/EntityModule%3A-Looting) | looting configuration of mob | |
| attributes | attribute list | a list of attribute modifiers applied | |
| skills | [section](https://github.com/Blutkrone/RPGCoreV3/wiki/EntityModule:-Creatures#skills) | either a custom skill or some linked skills | |
| spawn-egg | [section](https://github.com/Blutkrone/RPGCoreV3/wiki/EntityModule:-Creatures#spawnegg) | an item configuration for an itemized spawning egg | |

## Special Note: Tags

When mobs are spawned via spawners they are processed as general hostile entities. So do **not** manually add players to hostility tags, when a mob is considered general hostile they receive the following things:

1. Entity tag: "PLAYER_HOSTILE"
2. Hostile tag: "PLAYER"
3. Friendly tag: "PLAYER_HOSTILE"

The friendly tag is **only** received should you have no friendly tags defined manually.

# Disguises

Prequisite (1): https://www.spigotmc.org/resources/libs-disguises.32453/  
Prequisite (2): https://www.spigotmc.org/resources/rpgcore-libsdisguises-bridge-v1-13-v1-15.72994/  
Recommended: https://mineskin.org/

| Option | Type | Description | Required |
|-|-|-|-|
| | | | |
| display.disguise.raw | string | disguise string within the libsdisguise specifications | required |
| display.disguise.player | string | custom name of player | |
| display.disguise.name | string | custom display name override | |
| display.disguise.signature | base64 string | custom skin signature of a player | |
| display.disguise.encoded | base64 string | custom skin encoding of a player | |
| display.disguise.baby | boolean | use baby form of the mob | |
| display.disguise.equipment | item list | either a material or an rpgcore item, lead with [slot](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/inventory/EquipmentSlot.html) | |

Example usage of a disguise, transforms a zombie into a player using a certain skin. You can research libsdisguises yourself to figure out more advanced disguises.

```yml
  display:
    type: ZOMBIE
    name: 'Undying Vagabond'
    disguise:
      # The raw form of the disguise utilized
      raw: 'player %player% setSkin {"id":"a149f81bf7844f8987c554afdd4db533","name":"libraryaddict","properties":[{"signature":"%signature%","name":"textures","value":"%encoded%"}]}'
      # Identity of player to queue up
      player: rpgcoredummy
      # Adjust Parameters here, you may use something like https://mineskin.org/ to generate the parameters passed here
      # Skin Url: http://textures.minecraft.net/texture/eda48e190e604b999f3da1754804b8045c8c581eecee53c74ea8881257e22d63
      signature: 'FiGCdX0UD8GkiZw3h/HFghzwJAZhePfbQGX5jmxaS/UJX3D8Xc6ftpyhILCJeu7IZJs7+Eao6avmoOLaEETlfs/FyYAEE4YpujN4kjNnn2VBMDPi3hfMyPbap7P2iheh7hmT8kjx8n1jFVkh3wiNmOfsC5b+BYvkHQIDQp6kEviIDo5Jl1mGy7t9U18wm1QXMi83uCNsDOvgR/xPxxQxlJ45gcr5MoDh3YDAPZ5nPwGe3TL7/SVQb2wvn0GJ3wcy0sOx7scyWaXnkL3U0HIS7iw8LD8ucleKXQQP1HTcy9Rg/d5eCcZ4D3R+5nq13a6e/y5D5pvYLVAMyTInlW3jokcN+Iirk4Grbis8pk7TJMb8a5DWVpIR2AMJjDPSt+o7saFO0neLPhNHkrpfUvlVwUyEhvU8W3GY4gfvqrOGJKQ4rcsRGyPnpaYKjSoGnEz4NkhpwZ7tPao7keaR2haDuXQC0P3nZmeUVpLTS8OJbWMwh6jd+Bjl9RV5ltIUk/FMAUc01lBmXDl1iVi2uSCEF/3gbrQ5RqtQV4LcVziiD6DPPSdzsmrns6bboOo1MqbcNHq+IbbZz6uZwrZ+WARa6fDnMbnM5Squ7vfy8SlgjkhC6Qw7kcctZsRbAreScZWOivbTRuryU/YaS3Pwd6PjQGQlpAFSfCpuZ/mmtO8Ro44='
      # Encoding of skin utilized
      encoded: 'eyJ0aW1lc3RhbXAiOjE1NzQ0MjI2MjU4NjMsInByb2ZpbGVJZCI6IjgyYzYwNmM1YzY1MjRiNzk4YjkxYTEyZDNhNjE2OTc3IiwicHJvZmlsZU5hbWUiOiJOb3ROb3RvcmlvdXNOZW1vIiwic2lnbmF0dXJlUmVxdWlyZWQiOnRydWUsInRleHR1cmVzIjp7IlNLSU4iOnsidXJsIjoiaHR0cDovL3RleHR1cmVzLm1pbmVjcmFmdC5uZXQvdGV4dHVyZS9lZGE0OGUxOTBlNjA0Yjk5OWYzZGExNzU0ODA0YjgwNDVjOGM1ODFlZWNlZTUzYzc0ZWE4ODgxMjU3ZTIyZDYzIn19fQ=='

```

# Skills

You can define a custom skill within the skill configuration of a mob, allowing you to generate a unique behaviour specific to this mob. This is a complete skill, and the mob will always acquire the primary behaviour on spawning.

```yml
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

## Spawnegg

This is an complete item configuration, see [[ItemModule: Items]] for further details. You can define it as a normal item in the item module too, just make sure to use the correct spawn-egg-id (it is automatically written when a part of the mob.)

| Option | Type | Description | Defaults |
|-|-|-|-|
| | | | |
| custom-tags.spawn-egg-level | integer | level of the spawned mob | |
| custom-tags.spawn-egg-id | string | the mob id, will be force written | |