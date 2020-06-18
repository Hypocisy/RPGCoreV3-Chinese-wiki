Directory: "./../SkillModule/ailments.yml"  
Module: SkillModule, DamageModule

Ailments are global skills which are meant to be used to give certain damage types their own identity. Allow fire damage to burn enemies, lightning damage to cause a thunderstrike, chaos damage to inflict poison, cold damage to inflict a slowing effect and physical damage to impale enemies.

You have the full skill system available for Ailments.

Below you can see an example for how to implement an ignite ailment, with the following rules:

1. Ignite effect lasts 5 seconds (100 ticks)
2. Ignite adds 30% of proccing damage to burning damage
3. Normal hits have a 10% chance of inflicting ignite
4. Critical hits always inflict ignite on the enemy
5. Duration, effect and chance can be scaled globally

```yml
fire-ailment:
  id: AILMENT_IGNITE
  variable-register:
    IGNITE_DURATION: 
      value: 100
      absolute-tags: [AILMENT_DURATION]
    IGNITE_EFFECT: 
      value: 30
      absolute-tags: [AILMENT_EFFECT]
    IGNITE_CHANCE: 
      value: 10
      absolute-tags: [AILMENT_CHANCE]
  behaviours:
    INFLICT_AILMENT_CRIT:
      ailment-entry: true
      trigger: deal-damage{wanted-types=CRITICAL,HIT;use-and=true;element=FIRE}
      actions:
      - "ignite{duration=IGNITE_DURATION;inherited=[ADD (IGNITE_EFFECT/100)*EVENT_DAMAGE_FIRE TO DAMAGE_FIRE]}@target"
    INFLICT_AILMENT_CHANCE:
      ailment-entry: true
      trigger: deal-damage{chance=IGNITE_CHANCE/100;wanted-types=HIT;use-and=true;element=FIRE}
      actions:
      - "ignite{duration=IGNITE_DURATION;inherited=[ADD (IGNITE_EFFECT/100)*EVENT_DAMAGE_FIRE TO DAMAGE_FIRE]}@target"
```

