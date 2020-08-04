Directory: "./../Language"  
Module: Language

The language module is handling the majority of general translation aspects, however note that some things (e.G: skill descriptions, item displayname, passive tree nodes etc) would be handled by their local module rather then the language module.

# Configuration (./../Language/config.yml)

The general configuration options of the language module.

| Option | Type | Description |
|-|-|-|
| line-prefix | string | added right at the start of a language pattern  |
| amount-prefix | string | added before the amount is written in a language pattern |
| amount-prefix | string | added after the amount is written in a language pattern |
| trim-excess-spaces | boolean | should the logic result in multiple empty spaces, trims these away |
| perfect-amount-prefix | string | when the attribute is on an item, and greater-equal to the limit |
| perfect-amount-suffix| string | when the attribute is on an item, and greater-equal to the limit |
| skill-level-scaling-pattern | string | pattern for the scaling of an explicit skill its level |
| level-keywords | section | refers to the three ways an attribute can be affected |
| chest-gui-title | section | titles of the respective chest gui interfaces |
| passive-tree | section | details of the navigation elements of the passive tree |
| general-mappings | section | usually meant to send messages to players, start up will list the latest |
| note-when-jewel | string list | extra description to indicate how to socket a jewel |
| note-when-skill | string list | extra description to indicate how to socket a skill |

# Writing a language pattern (./../Language/default-language.yml)

A language string accepts placeholders like `{AMOUNT:TYPE}`, for example if you want to display the amount of health like `+148 to maximum health` you would use `{AMOUNT:INTEGER} to maximum health` while wanting to see something like `+1.3% to crit chance with attacks` would require `{AMOUNT:PERCENT} to crit chance with attacks` as the formatter.

# Creating the language patterns for attributes (./../Language/default-language.yml)

Should you want to avoid writing an almost identical language pattern almost a hundred times to cover the slight modifications of it, you can use the assisted mappings to help you generating permutations. File these under the `assisted-mapping` section

```yml
  LEECHING_RATE:
    # the attribute we are creating a language pattern for
    template-attribute: "LEECH_AS_{0}_{1}"
    # the language pattern we generate for the attribute
    template-description: "{AMOUNT:PERCENT} {LEVEL} {0} leeched from {1} damage"
    # the substitutes for the placeholders
    substitution:
      # substitute A0 (attribute {0})
      'A0': [HEALTH, SHIELD, MANA]
      # substitute D0 (description {0})
      'D0': [health, shield, mana]
      # substitute A1 (attribute {1})
      'A1': [PHYSICAL, FIRE, COLD, LIGHTNING, CHAOS]
      # substitute D1 (description {1})
      'D1': [physical, fire, cold, lightning, chaos]

```

While it will result in longer substitution lists, it is somewhat more compact otherwise. Should you dislike utilizing the assisted mappings, you can write them per hand at the `static-mapping` section like:

```yml
LEECH_AS_HEALTH_FIRE: "{AMOUNT:PERCENT} {LEVEL} health leeched from fire damage"
LEECH_AS_HEALTH_COLD: "{AMOUNT:PERCENT} {LEVEL} health leeched from cold damage"
...
LEECH_AS_MANA_CHAOS: "{AMOUNT:PERCENT} {LEVEL} mana leeched from chaos damage"
```

# Formatting types that are accepted 

When formatting a number, you can utilize the following ways for formatting them (this is used across the whole core.) Should a wrong type be defined you will fallback to formatting as a decimal.

| Option | Description | Example (1) | Example (2) |
|-|-|-|-|
| PERCENT | formats a decimal as a percentage | 0.08 <=> +8% | 1.58 <=> +158% |
| INT_PERCENT | formats a integer as a percentage | 113 <=> +113% | 11.5 <=> +11% |
| DECIMAL | formats a decimal to 1 comma digit | 1.581 <=> 1.5 | 3.2 <=> 3.2 |
| BOOLEAN | greater-equal formatted into "yes" | 0.94 <=> "No" | 1.04 <=> "Yes" |
| TICK_SECONDS | ticks converted to seconds | 58 <=> "2.9s" | 10 <=> "0.5s" |
| TICK_TIME | ticks converted to seconds | 58 <=> "2.9s" | 10 <=> "0.5s" |
| SECONDS | ticks converted to mm:ss | 580 <=> 00:29 | 24220 <=> 20:11 |
| TIME | ticks converted to mm:ss | 580 <=> 00:29 | 24220 <=> 20:11 |
