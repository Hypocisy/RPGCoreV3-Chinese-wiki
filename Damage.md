The modifiers listed in the "setup" section ("ADD ... TO ...") can resolve variables!

Should the immediate trigger be a damage trigger and the damage inflicted be tagged as "NOCHILD" we will cancel. Anything that may create a feedback loop should be designed in a manner where it is blocked by a cooldown. 

You might want to check the [[DamageModule: Hardcoded Behaviour]] and [[DamageModule: Customizing Damage]] articles, the [[CraftDamageModule]] article may also prove useful.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | string | | damage | yes | no |
| types | list | types of damage to tag | | yes | no |
| setup | list | combat attributes to use | | yes | partial |
| scale-off-parent | boolean | attacker set to parent | false | no | no |
| baked | boolean | makes values static, better for performance | false | no | no |
| unmodifiable | boolean | prevents modifications to the damage | false | no | no |
| silent | boolean | will suppress **custom** sounds to be played | false | no | no |
| not-considered-skill | boolean | set to true to remove "SKILL" damage type | false | no | no |