Directory: "./../FlagModule.yml"  
Module: FlagModule

This is an internal module with little to nothing being exposed for configuration, as the functionality is driven by other modules. You can access the functionality with the [[Update Flag]] and [[Check Flag]] parts of the skill system, to check and add other flags to an entity.

## Default Flags

The attribute refers to the ticks before advancing the state, if no attribute is defined it means that it cannot be modified. You may manually define the attribute in the [[CustomAttributeModule]] should you want, but be warned that this may result in a drop in performance. The attribute defaults to 80, making a flag update every 4 seconds.

The attribute is "CYCLE_" followed by the Id of the flag.

| Flag | Type | Description | Attribute |
|-|-|-|-|
| ENGAGED | Temporary Boolean | When attacked by another entity with "HIT" type damage | yes |
| TOOK_# | Temporary Boolean | All elements and damage types are added | no |
| DODGED_RECENTLY | Temporary Boolean | Avoided damage by dodging recently | yes |
| BLOCKED_RECENTLY | Temporary Boolean | Avoided damage by blocking recently | yes |
| CULLED_RECENTLY | Temporary Boolean | Inflicted culling recently | yes |
| KILLED_RECENTLY | Temporary Boolean | Killed someone recently | yes |
| LEECHED_RECENTLY_HEALTH | Temporary Boolean | Recovered health from leeching recently | yes |
| LEECHED_RECENTLY_SHIELD | Temporary Boolean | Recovered shield from leeching recently | yes |
| LEECHED_RECENTLY_MANA | Temporary Boolean | Recovered mana from leeching recently | yes |