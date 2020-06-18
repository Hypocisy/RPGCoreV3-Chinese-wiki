Directory: "./../SkillModule/ailments.yml"  
Module: SkillModule, DamageModule

This article intentionally is listed with both the DamageModule and SkillModule, as it relates to both of them. Ailments are considered global skills which are meant to be used to extend on the mechanics of damage output. It lets you give special effects to damage by their element.

# How to create an ailment

A damage ailment is implemented exactly like how other skills are, the only difference being that every entity receives the skill for it upon spawning. Like that you can use a damage trigger to identify when the skill owner deals damage, and make them inflict a certain effect on their target.

Below you can see an example for how to implement an ignite ailment, when someone burns they take 30% of the damage which procced the ignite as fire damage every time the ignite ticks. Crit damage always applies the ailment, while normal damage only has a certain chance to inflict it. You can scale this ailment in a targetted fashion (iE: IGNITE_DURATION) or scale all ailments at once (iE: AILMENT_DURATION)

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

