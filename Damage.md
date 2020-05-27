The modifiers listed in the "setup" section ("ADD ... TO ...") can resolve variables!

Should the immediate trigger be a damage trigger and the damage inflicted be tagged as "NOCHILD" we will cancel. Anything that may create a feedback loop should be designed in a manner where it is blocked by a cooldown. 

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | string | | damage | yes | no |
| types | list | damage types (HIT, SPELL, ...) which we are marking this with | | yes | no |
| setup | list | combat attributes to utilize | | yes | partial |
| scale-off-parent | boolean | attacker set to parent | false | no | no |
| baked | boolean | makes values static, better for performance | false | no | no |
| unmodifiable | boolean | prevents modifications to the damage | false | no | no |
| silent | boolean | will suppress **custom** sounds to be played | false | no | no |
| not-considered-skill | boolean | set to true to remove "SKILL" damage type | false | no | no |