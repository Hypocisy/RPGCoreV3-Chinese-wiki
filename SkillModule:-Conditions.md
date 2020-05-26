Directory: "./../skillmodule/skills"  
Module: SkillModule

Conditions are used to narrow down targets, usually whenever you can input a condition you may also input a targetter - as the eventual check is more about what remains rather then why something remains. Read more about the [[layered]] targetter should you intend to mix targetters together like that.

# Available Conditions

| | | | | |
|-|-|-|-|-|
| [[angle]] | [[random]] | [[friendly]] | [[hostile]] | [[material]] |
| [[solid]] | [[random-variable]] | [[grounded]] | [[sprinting]] | [[submerged]] |
| [[falling]] | [[burning]] | [[remaining]] | [[behind]] | [[flag-condition]] |
| [[blocking]] | [[attached]] | [[variable]] | [[unobstructed]] | [[potion]] |
| [[crouching]] | [[linked-slot]] | [[equipped]] | [[event-data]] | [[entity-type]] |
| [[soul-condition]] | [[worldguard]] | [[time]] | [[biome]] | [[rpgcore-type]] |

# Configuration of Conditions

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| inverted | boolean | inverts the result of the condition | false | no | no |
| scale-off-parent | boolean | replaces the asker with the parent of the behaviour | false | no | no |