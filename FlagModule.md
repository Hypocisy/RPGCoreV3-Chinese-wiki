Directory: "./../FlagModule.yml"  
Module: FlagModule

This is an internal module with little to nothing being exposed for configuration, as the functionality is driven by other modules. You can access the functionality with the [[Update Flag]] and [[Has Flag]] parts of the skill system, to check and add other flags to an entity.

## Default Flags

The attribute refers to the ticks before advancing the state, if no attribute is defined it means that it cannot be modified. You may manually define the attribute in the [[CustomAttributeModule]] should you want, but be warned that this may result in a drop in performance.

| Flag | Type | Description | Attribute |
|-|-|-|-|
| ENGAGED | 

## Attribute

An attribute with "CYCLE_\<id\>" is generated, defaulting to 80 by default. This is the rate at which the flag will try to update to the next state. You may adjust the parameter.