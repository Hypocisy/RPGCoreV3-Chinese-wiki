Shoot a minecraft projectile from the target location (experimental)

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | / | / | craftprojectile | / | / |
| count | integer | total of projectiles shot | 1 | no | yes |
| random | decimal | scattering of the arrows | 0.15 | no | yes |
| force | decimal | power of arrow shot | 0.7 | no | yes |
| type | [Entity Type](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/entity/EntityType.html) | Must be a projectile type | ARROW | no | no |
| setup | Modifier List | List of modifiers that are appended to the projectile damage | | no | no |