Directory: "./../DamageModule.yml"  
Module: DamageModule

## Conversion Behaviour

Conversion transforms damage from element to each other, allowing you to benefit from both of the elements at once. This refers both to the defensive and offensive modifiers. 

Should you deal 10% increased fire and cold damage, converting all damage from fire to cold would be like dealing 20% increased cold damage. But if your enemy has 20% fire and cold resistance, it would be like if hitting someone with a 40% cold resistance. 

This applies to **every** modifier for damage, partial conversion is possible. If conversion exceeds 100% it will be normalized (ex: 75% phys to cold, 75% phys to lighting => 50% phys to cold, 50% phys to lightning)

| Entity Attribute | Combat Attribute | Description |
|-|-|-|
| DEAL_%A%_AS_%B% | DEAL_%A%_AS_%B% | Attacker converts damage dealt from A to B |
| TAKE_%A%_AS_%B% | TAKE_%A%_AS_%B% | Defender converts damage taken from A to B |

## Leeching Behaviour

Leeching absorbs a part of the damage to recover over a certain time period, while instant leech grants it to you instanteously. 

| Entity Attribute | Combat Attribute | Description |
|-|-|-|
| MAXIMUM_LEECH_AS_%RESOURCE% | / | Maximum percentage per second recovered |
| OVERLEECH_DURATION_%RESOURCE% | / | Ticks to keep leeching while on full resource |
| LEECH_AS_%RESOURCE%_%ELEMENT% | LEECH_AS_%RESOURCE%_%ELEMENT% | Fraction of damage leeched over time |
| LEECH_AS_%RESOURCE%_%ELEMENT% | LEECH_AS_%RESOURCE%_%ELEMENT% | Fraction of damage leeched instantly |

## Avoidance Behaviour

Avoidance allows you to block or dodge damage, there is no internal difference between either of these two. It is a passively ocurring chance, adding the "DODGED" or "BLOCKED" damage type if it ocurrs and fixes the damage output at zero. Dodging is rolled before blocking.

| Entity Attribute | Combat Attribute | Description |
|-|-|-|
| DODGE_CHANCE | DODGE_CHANCE | chance to dodge damage and set it to 0 |
| BLOCK_CHANCE | BLOCK_CHANCE | chance to block damage and set it to 0 |

## Culling Behaviour

Culling refers to instant death once an enemy falls beneath the culling threshold.

| Entity Attribute | Combat Attribute | Description |
|-|-|-|
| CULLING_CHANCE | CULLING_CHANCE | chance to inflict culling |
| CULLING_THRESHOLD | CULLING_THRESHOLD | cull enemies below this percentage |

## Critical Behaviour

Crit damage is meant to apply a multiplier to the final resulting damage. Crit defense applies a reduction. The final multiplier would be written like `damage = damage * (1 + (crit_damage)*(1-crit_defense))` meaning that a 100% crit defense means you do not take any additional damage from crits.

| Entity Attribute | Combat Attribute | Description |
|-|-|-|
| CRIT_CHANCE_%TYPE% | CRIT_CHANCE | chance to inflict a critical blow |
| CRIT_DAMAGE_%TYPE% | CRIT_DAMAGE | damage multiplier gained with crits |
| CRIT_DEFENSE_%TYPE% | CRIT_DEFENSE | reduction of extra damage taken from crits |