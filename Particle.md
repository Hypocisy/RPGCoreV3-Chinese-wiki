Sends particles to the nearby players, different particle classes accept different additional arguments. The direction is relative to the input target.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | string | / | particle | / | / |
| class | particle class | general particle configuration to use | SINGLE | yes | no |
| points | integer | number of points to use while drawing | 20 | no | yes |
| draw-per-tick | integer | points to draw in one ticking | 20 | no | yes |
| draw-interval | integer | time between each drawing tick | 1 | no | yes |
| yoffset | decimal | offset the spawning point | 0 | no | yes |

# Defining a particle

Should you use the string notation, you may only have one type of a particle used. But should you use the extended notation (a full section) you can mix a bigger number of particles together.

If you wish particles to have directions, you must set the amount to 0 - like that the particle class you went for will input direction.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| multi-particle | section | a section with multiple particle configurations | / | no | no |
| particle | Particle | [Particle](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Particle.html) to use | REDSTONE | no | no |
| speed | decimal | motion speed of particle | no | no |
| size | decimal | size of particle | 1 | no | no |
| amount | integer | number of particles | 0 | no | no |
| color | color | rgb number representing coloring | | no | no |
| material | Material | [Material](https://github.com/CryptoMorin/XSeries/blob/master/src/main/java/com/cryptomorin/xseries/XMaterial.java) to use | | no | no |

## Single Particle

Draw a single particle at a specific point.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| | | | | | |

## Circle Particle

Draw a cirlce of particles

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| radius | decimal | radius of circle | 2 | no | yes |
| invert | boolean | inverted particle direction | false | no | no |

## Spiral Particle

Draw a spiral of particles

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| radius | decimal | radius of circle | 2 | no | yes |
| height | decimal | height of spiral | 1 | no | yes |
| angle | decimal | angle to spiral | 360 | no | yes |

## Line Particle

Draw a line of particles

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| length | decimal | length of line | 2 | no | yes |

## Cone Particle

Draw a cone of particles. A cone with a 360 angle and a minimum radius of 0 will be a disc.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| min-radius | decimal | cone minimum radius | 0 | no | yes |
| max-radius | decimal | cone maximum radius | 1 | no | yes |
| angle | decimal | angle of cone | 60 | no | yes |
| points | integer | density of points per unit | 4 | no | yes |

## Sphere Particle 

Draw a (hollowed!) sphere of particles.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| radius | decimal | radius of sphere | 2 | no | yes |
| invert | boolean | inverted particle direction | false | no | no |


## Pillar Particle 

Draw a number of pillars in a circle

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| radius | decimal | radius of pillar circle | 2 | no | yes |
| length | decimal | length of pillars | 1 | no | yes |
| total | integer | total of pillars drawn | 7 | no | yes |
| shift | decimal | pillar rotation shifting | 0 | no | yes |
| invert | boolean | inverted particle direction | false | no | no |