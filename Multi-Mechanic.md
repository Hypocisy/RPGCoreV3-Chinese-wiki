A wrapper allowing you to execute multiple mechanics at once. **You cannot use the string form for this,** you need to define an extended section! With the exception of a rare edge case, it should not be necessary to use this mechanic.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | string | | multi | yes | no |
| mechanics | string list | ids under which the mechanics are keyed in the parent skill | | no | no |
| actions | string list or section | will behave like an extension of an action list of a behaviour | | no | no |

## How to use the Multi Mechanic

```yml
example_skill:
  id: example_id
  name: Example Skill
  # ...
  mechanics:
    MULTI_MECHANIC_EXAMPLE:
      type: multi
      # all these mechanics are run on the target
      mechanics:
      - "sound{pitch=0.125;volume=0;sound=ENTITY_GENERIC_EXPLODE}"
      - "particle{class=SINGLE;particle=REDSTONE}"
      # these are executed as normal actions like other behaviours
      actions:
      - "particle{class=SINGLE;particle=SNOW_SHOVEL}@target"
      - "particle{class=SINGLE;particle=SNOW_SHOVEL}@self"
  behaviours:
    PROC_ON_HIT:
      primary: true
      # proc when we take damage, default target is the damaged
      trigger: deal-damage{finished=true;wanted-types=MELEE}
      # run the mechanic at the target we damaged
      actions:
      - "MULTI_MECHANIC_EXAMPLE@target"
```