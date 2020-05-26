Directory: "./../DamageModule.yml"  
Module: DamageModule

Beneath you can find a listing of hardcoded systems, you may avoid putting them into use by not permitting your players to invest into them.

## Technical Behaviour

There are a number of technical limitations when using the damage module, such as that damage always has to belong to a type and an element. There is a number of hardcoded types, which you can find in [[CraftDamageModule]], but weapons can be made to add extra types and skills have great freedom aswell.

## Conversion Behaviour

Conversion transforms damage from element to each other, allowing you to benefit from both of the elements at once. This refers both to the defensive and offensive modifiers. 

Should you deal 10% increased fire and cold damage, converting all damage from fire to cold would be like dealing 20% increased cold damage. But if your enemy has 20% fire and cold resistance, it would be like if hitting someone with a 40% cold resistance. 

This applies to **every** modifier for damage, partial conversion is possible. If conversion exceeds 100% it will be normalized (ex: 75% phys to cold, 75% phys to lighting => 50% phys to cold, 50% phys to lightning)

| Entity Attribute | Combat Attribute | Description |
|-|-|-|
| DEAL\_%A%\_AS\_%B% | DEAL\_%A%\_AS\_%B% | Attacker converts damage dealt from A to B |
| TAKE\_%A%\_AS\_%B% | TAKE\_%A%\_AS\_%B% | Defender converts damage taken from A to B |

## Leeching Behaviour

Leeching absorbs a part of the damage to recover over a certain time period, while instant leech grants it to you instanteously. 

| Entity Attribute | Combat Attribute | Description |
|-|-|-|
| MAXIMUM\_LEECH_AS\_%RESOURCE% | / | Maximum percentage per second recovered |
| OVERLEECH\_DURATION\_%RESOURCE% | / | Ticks to keep leeching while on full resource |
| LEECH\_AS\_%RESOURCE%\_%ELEMENT% | LEECH\_AS\_%RESOURCE%\_%ELEMENT% | Fraction of damage leeched over time |
| LEECH\_AS\_%RESOURCE%\_%ELEMENT% | LEECH\_AS\_%RESOURCE%\_%ELEMENT% | Fraction of damage leeched instantly |

## Avoidance Behaviour

Avoidance allows you to block or dodge damage, there is no internal difference between either of these two. It is a passively ocurring chance, adding the "DODGED" or "BLOCKED" damage type if it ocurrs and fixes the damage output at zero. Dodging is rolled before blocking.

| Entity Attribute | Combat Attribute | Description |
|-|-|-|
| DODGE\_CHANCE | DODGE\_CHANCE | chance to dodge damage and set it to 0 |
| BLOCK\_CHANCE | BLOCK\_CHANCE | chance to block damage and set it to 0 |

## Culling Behaviour

Culling refers to instant death once an enemy falls beneath the culling threshold.

| Entity Attribute | Combat Attribute | Description |
|-|-|-|
| CULLING\_CHANCE | CULLING\_CHANCE | chance to inflict culling |
| CULLING\_THRESHOLD | CULLING\_THRESHOLD | cull enemies below this percentage |

## Critical Behaviour

Crit damage is meant to apply a multiplier to the final resulting damage. Crit defense applies a reduction. The final multiplier would be written like `damage = damage * (1 + (crit_damage)*(1-crit_defense))` meaning that a 100% crit defense means you do not take any additional damage from crits.

| Entity Attribute | Combat Attribute | Description |
|-|-|-|
| CRIT\_CHANCE\_%TYPE% | CRIT\_CHANCE | chance to inflict a critical blow |
| CRIT\_DAMAGE\_%TYPE% | CRIT\_DAMAGE | damage multiplier gained with crits |
| CRIT\_DEFENSE\_%TYPE% | CRIT\_DEFENSE | reduction of extra damage taken from crits |