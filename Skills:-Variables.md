Directory: "./../Skills"  
Module: Skills

Variables are accessible across the whole skill system. **Some** of these variables may also be accessed as an entity attribute, but should be avoided as much as possible (the implementation is optimized for the skill system, not for entity attributes!) 

## Red Variables, Golden Variables

The description of a skill may show up two types colors. When a variable is colored red, it means that we are dealing with an approximation. When a variable is colored yellow, it is the latest state of it. Red numbers should be identical for everyone, but yellow numbers tend to differ a fair bit.

## Utilizing Variables

A variable is expected to be written like

```yml
    # Scale with the "CAST_TIME" skill attribute
    CAST_TIME:
      # the formula defining the variable
      value: 60-LEVEL
      # The "CAST_TIME:INTELLIGENCE", "CAST_TIME:BUFF" and "CAST_TIME:SPELL" 
      #  skill attributes will also scale the variable
      tags: [INTELLIGENCE, BUFF, SPELL]
      # The "CASTER_MODIFIER" skill attribute will also scale the variable
      absolute-tags: [CASTER_MODIFIER]
```

Where value is evaluated when requested, the tags allow for easier global modification of it. 

For example, if you want to offer something like "Reduced cast time for buff skills" you could reference "CAST_TIME:BUFF" if you want something like "Reduced cast time for all spells" you could reference "CAST_TIME:SPELL" for it. Excluding the latter half, just modifying "CAST_TIME" will skip any checks.

The special tags "TOME", "TRAP", "TOTEM", "TRIGGERED" are automatically added based on which trigger caused it. Triggered refers to the "signal" trigger.

## A listing of all variables

Variables are specific values, make sure to respect upper-lower case. Some variables are only available if it makes sense for them to be available. For example, checking the OVERKILL_AMOUNT while running a timer trigger will not make any sense. 

| Variable | Purpose |
|-|-|
| LVL/LEVEL | Level of the attached skill, 0 if undefined. The level is based on the skill which granted us the skill. |
| ATTACHMENT_REMAINING_DURATION | If defined, highest remaining duration |
| ATTACHMENT_CURRENT_STACKS| If defined, current stack count |
| ATTACHMENT_MAX_STACKS| If defined, maximum number of stacks this attached behaviour can have |
| ATTACHMENT_MAX_DURATION| If defined, duration which this attached behaviour refreshes to |
| LOCAL_POS | If defined, the index of the skill within its contained skill link |
| GLOBAL_POS | If defined, the index of the skill within the item | 
| SELF_<...> | Remaining Health, Shield, Mana or Attribute of behaviour owner |
| PARENT_<...> | Remaining Health, Shield, Mana or Attrbiute of behaviour giver |
| SELF_LEVEL | If defined the level of the entity |
| PARENT_LEVEL | If defined the level of the parent that attached the behaviour |
| TARGET_LEVEL | If defined the target inherited by the targetter |
| SELF_BLOCKPOWER | Block power (used with offhand shield items) that remains of the owner | 
| PARENT_BLOCKPOWER | Block power (used with offhand shield items) that remains of the parent | 
| TARGET_BLOCKPOWER | Block power (used with offhand shield items) that remains of the target | 
| TRAP_BURST_CHAIN | A single burst chain refers to traps that popped in a connected fashion, this will increment as the traps keep popping |
| ACTIVE_TOTEM_TOTAL | current number of placed totems |
| ACTIVE_TRAP_TOTAL | current number of placed traps |
| EVENT_DAMAGE_%ELEMENT% | final damage result, only with damage triggers |
| OVERKILL_AMOUNT | damage exceeding health, only with killing triggers |
| CURRENT_INTERVAL | how often the mechanic was repeated |
| CHANNELING_INTERVAL | how often was the channeling procced, only with channeling triggers |

## Default Functions

Functions relative to the asking party.

| Function | Purpose |
|-|-|
| STACKS | accept id of behaviour we are checking, current stack count of a certain attachment |
| DURATION | accept id of behaviour we are checking, remaining duration of a certain attachment |
| MAXSTACKS | accept id of behaviour we are checking, maximum stack count of a certain attachment |
| MAXDURATION | accept id of behaviour we are checking, maximum duration of a certain attachment |