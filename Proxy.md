A "proxy" is a temporary extension of a creature with its own subset of rules and actions. A proxy communicates with the caster using local signals. Currently there are only two proxy types implemented, but more may be introduced.

Important note: The 'signal' behaviours are **required** to be assigned as PRIMARY behaviours alongside the behaviour responsible for summoning them (otherwise the proxy wont be able to find the trigger, hence the actions cannot be executed.)

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | string | / | proxy | / | / |
| proxy | proxy type | The type of a proxy which we are dealing with | | yes | no |
| friendly | boolean | the unique logic (Fork, Chain, Pierce) etc is based off this | false | no | no |
| maximum-age | ticks | how many ticks before the proxy is removed | 200 | no | yes |
| interval | ticks | fire the tick signal at this interval | 5 | no | yes |
| total | integer | copies of the proxy to summon at once | 1 | no | yes |
| diameter | decimal | diameter used to detect collission | 1 | no | yes |
| drag | decimal | drag factor to determine velocity loss | 0.05 | no | yes |
| speed | integer | iterations to run per tick | 1 | no | yes |
| y-offset | decimal | vertical offset when summoned | 1 | no | yes |
| signal-prefix | string | prefixes the signals fired if defined | | no | no |
| velocity-x/y/z | percentage | velocity multiplier applied | 100% | no | yes |
| representing-item | material | will attach an item to the proxy | / | no | no |
| representing-custom-model | integer | uses a custom model data tag for the item (1.12+) | / | no | no |

## Proxy Type: METEOR

Will summon a meteor that will descend vertically, it will always face the target location and the spread factor can control the vertical angle it will fall at.

Fires following signals: PROXY_COLLIDED, PROXY_TICKED, PROXY_DESTROYED

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| spread | decimal | maximum distance on X-Z axis from the target | | no | yes |

## Proxy Type: PROJECTILE

Will summon a projectile that flies in a straight line, it can potentially pierce through entities but not blocks.

Fires following signals: PROXY_COLLIDED, PROXY_TICKED, PROXY_DESTROYED

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| angle | decimal | spread angle when the projectiles are summoned (perfect distribution) | 120 | no | yes |
| pierces | integer | entities to pierce through | 0 | no | yes |
| forks | integer | how often we split after hitting an entity | 0 | no | yes |
| chains | integer | jumps to another entity when hitting | 0 | no | yes |
| offset | decimal | forward offset of the projectile | 1.5 | no | yes |
| flatten | decimal | reduce the y-axis direction by a percentage (0.0-1.0) | 0.0 | no | yes |
| random-inertia | random initial inertia when releasing projectile, optimal for missile | 0.0 | no | yes |
| missile | targetter | missile will chase an initial target | no | no | 

## An example of how to use a proxy

Beneath is the implementation of a skill using a proxy, beware that this is only meant to give you an idea about how to structure such skills.

```yml
FIREBALL:
  id: FIREBALL
  name: Fireball
  behaviours:
    CAST_VIA_TOME:
      primary: true
      trigger: dummy{}
      actions:
      # Release the proxy as a projectile, signals use the namespace "FIREBALL"
      - "proxy{proxy=PROJECTILE;speed=10;total=1;signal-prefix=FIREBALL}@target"
    ON_TICK:
      primary: true
      secondary: true
      secondary: true
      trigger: "signal{channel=FIREBALL:PROXY_TICKED}"
      actions:
      # stuff to do when the proxy is ticked 
    ON_COLLIDE:
      primary: true
      secondary: true
      secondary: true
      trigger: "signal{channel=FIREBALL:PROXY_COLLIDED}"
      actions:
      # stuff to do when the proxy collided with something
    ON_DESTROY:
      primary: true
      secondary: true
      secondary: true
      trigger: "signal{channel=FIREBALL:PROXY_DESTROYED}"
      actions:
      # stuff to do when the proxy is destroyed
```