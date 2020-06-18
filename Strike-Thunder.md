A minecraft lightning bolt will strike the target position, this does **not** discriminate who is present! You may end up striking your allies.

Note that using this will make the thunder damage scale off the caster, when thunder procs the "MC_LIGHTNING" is added as a damage type. Lightning damage also is considered a hit.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | / | / | thunder, lightning | / | / |
| fake | boolean | just emulate thunder without it actually happening | false | no | no |