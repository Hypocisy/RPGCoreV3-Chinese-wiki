Triggers responsible for natural minecraft projectiles, you also can use the [[Take Damage]] or [[Deal Damage]] trigger instead, checking for projectile damage types. This one is specific to identify the advanced mechanics.

# Your arrow hit the target

Triggered when someone deals damage with an fired arrow

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | / | / | myarrowhit | / | / |
| permit-regular | boolean | arrow can be a regular one | true | no | no |
| permit-chained| boolean | arrow can be a chained one | false | no | no |
| permit-forked| boolean | arrow can be a forked one | false | no | no |
| permit-pierced| boolean | arrow can be a pierced one | false | no | no |

# You were hit by an arrow

Triggered when someone takes damage from a fired arrow

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | / | / | hitbyarrow | / | / |
| permit-regular | boolean | arrow can be a regular one | true | no | no |
| permit-chained| boolean | arrow can be a chained one | false | no | no |
| permit-forked| boolean | arrow can be a forked one | false | no | no |
| permit-pierced| boolean | arrow can be a pierced one | false | no | no |
