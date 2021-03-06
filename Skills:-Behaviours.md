Directory: "./../Skills"  
Module: Skills

The skill system is built on behaviours. A behaviour is defined as a number of actions to be executed when a certain trigger is procced. The skill system is extremely advanced and flexible, much more so then the systems of most other resources, but putting it to use can prove quite a challenge.

Check the configuration examples and read the documentations for it.

# Configuration of Behaviours

The "BLOOD_MAGIC" skill attribute or "GLOBAL_BLOOD_MAGIC" entity attribute when evaluating to greater-equal 1 will transform mana consumption to health consumption. Beware that unlike mana, health reservation cannot fully reserve health (at least 1 point of health has to be unreserved.)

| Key & Aliases | Type | Description | Required | Variable |
| - | - | - | - | - |
| id | string | the unique id of the attachment | no | no |
| name | string | currently used for status effect icons | no | no |
| primary | boolean | acquired when first in link | no | no |
| secondary | boolean | acquired when not first in link | no | no |
| reservation-tag | string | require tag to be reserved for using | no | no |
| trigger | section or string | the trigger that has to be procced | yes | no |
| actions | list | mechanics applied to targets | yes | yes |
| persistent | boolean | makes a certain behaviour persistent | no | no |
| resource.flat | integer | flat cost of health, shield or mana | no | yes |
| resource.percent | percent | fractional cost of health, shield or mana | no | yes |
| resource.reservation | percent | percentage of health or mana to reserve | no | yes |
| attribute-effect.cluster | string | scales magnitude of the entity attribute effect | no | no |
| attribute-effect.effects | modifier list | while attached grants entity attributes | no | yes |

# About: Temporary behaviour persistence

**Warning:** Persistence is NOT designed for indefinite persistence. Mainly it is meant for effects which should last the full time, but may fail to do so. The persistence is interrupted should the server shut down, for the sake only a behaviour that was attached from the [[Attachment]] mechanic will be able to be saved.