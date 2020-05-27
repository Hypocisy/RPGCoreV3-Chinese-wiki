Generate a "trail" which interpolates between the last location and current location, allowing a number of actions to be executed for every point inbetween. No trail is generated if we moved more then 48 blocks in one go.

**This cannot be used in the string form.**

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| trail-repeat | integer | how often does the trail update | 1 | no | yes |
| trail-interval | integer | interval at which the trail updates | 1 | no | yes |
| trail-density | decimal | distance between points in the trail | 0.25 | no | yes |
| target-owned | boolean | apply trail to target, or apply to self | false | no | no |
| actions | action list | actions to execute on the generated points | | yes | no |

## How to use the Trail Mechanic

```yml
example_skill:
  id: example_id
  name: Example Skill
  # ...
  mechanics:
    TRAIL_MECHANIC_EXAMPLE:
      type: trail
      # Update very 0.5s
      trail-repeat: 2
      trail-interval: 10
      # execute every 0.25 units
      trail-density: 0.25
      # draw particles between the points
      actions:
      - "particle{class=SINGLE;particle=SNOW_SHOVEL}@target"
      - "particle{class=SINGLE;particle=SNOW_SHOVEL}@target"
  behaviours:
    PROC_ON_HIT:
      primary: true
      # proc when we take damage, default target is the damaged
      trigger: timer{interval=20}
      # run the mechanic at the target we damaged
      actions:
      - "TRAIL_MECHANIC_EXAMPLE@self"
```