Directory: "./../itemmodule/affixes"  
Module: ItemModule

Affixes reference to random modifiers on an item. An item will receive some random affixes upon being generated, the empty affix slots can be filled using [[ItemModule: Materials]] 

# Configuration (./../itemmodule/config.yml)

The general configuration option of the affixing system.

| Option | Type | Description |
|-|-|-|
| title | string | the title of the details to be printed on the item |
| multi-affix-chance | percentage | fill a slot until failing the roll, only on creation |
| slots-by-rarity | rarity mapping | rarity mapped to the extra affix slots on the item |
| affixing-groups | section | items may only roll affixes of their specific group |

# Configuration (./../itemmodule/items)

An item needs to be specified with a number of things so that it can roll affixes. Missing one of these may cause a failure, so make sure you got all of them defined.

If you define a negative number of affixes on the item, you can prevent item rarity from pushing the number up.

| Option | Type | Description |
|-|-|-|
| custom-tags.affixing-pool | string | only affixes of this group shall be rolled |
| custom-tags.default-affixes | integer | base amount of slots for affixes |

# Configuration (./../itemmodule/affixes)

You can define affixes like following

| Option | Type | Description |
|-|-|-|
| displayname | string | the name of the affix, currently unused |
| prefix | string | the name of the affix when it is a prefix, currently unused |
| suffix | string | the name of the affix when it is a suffix, currently unused | 
| effects | attribute list | attribute modifiers gained when equipping the item with the affix |
| support-skills | skill:level list | all skills will be supported by all skills listed here |
| main-skills | skill:level list | all skills socketed will also be supporting these skills |
| blocking-namespace | string | no two affixes of the same namespace may roll on the same item |
| weight | decimal | the relative chance compared to all other affixes to roll this one
| tier | integer | the tier, should start from from 1, of the affix. |
| force-description | string list | override auto generated documentation to show this instead, the text is static |

If you want to reduce your workload, you can utilize the generator notation to write the affixes. Define `auto-generator: true` as an option and instead of having to type every affix tier out by hand it will generate them in bulk

| Option | Type | Description |
|-|-|-|
| id-prefix | string | the namespace and prefix shared by all generated affixes |
| weight-scalar | formula | a formula where 0<=x<size calculcating the weighting of the generated affix | 
| generator.name-pool | string list | a list of strings defining the 'displayname' | 
| generator.prefix-pool | string list | a list of strings defining the 'prefix' | 
| generator.suffix-pool | string list | a list of strings defining the 'suffix' | 
| generator.effect-pool | nested attribute list | a list of attribute lists defining the 'effects' | 
| generator.support-pool | nested skill:level list | a list of skill lists defining the 'support-skills' |
| generator.skill-pool | nested skill:level list | a list of skill lists defining the 'main-skills' |
| generator.force-description | string list list | a list of string lists defining the 'force-description' |

Beware that "a list of lists" is not a typo, it specifically refers to something like

```yml
    effect-pool:
    - ["ADD 3 to INTELLIGENCE", "ADD 1 TO STAMINA"]
    - ["ADD 5 to INTELLIGENCE", "ADD 2 TO STAMINA"]
    - ["ADD 7 to INTELLIGENCE", "ADD 3 TO STAMINA"]
```