Directory: "./../Skills"  
Module: Skills

Conditions are used to narrow down targets, usually whenever you can input a condition you may also input a targetter - as the eventual check is more about what remains rather then why something remains. Read more about the [[layered]] targetter should you intend to mix targetters together like that.

# Available Conditions

| | | | | |
|-|-|-|-|-|
| [[Angle]] | [[Random]] | [[Friendly]] | [[Hostile]] | [[Material]] |
| [[Solid]] | [[Random Picked]] | [[Grounded]] | [[Sprinting]] | [[Submerged]] |
| [[Falling]] | [[Burning]] | [[Remaining]] | [[Behind]] | [[Check Flag]] |
| [[Blocking]] | [[Attached]] | [[Variable]] | [[Unobstructed]] | [[Has Potion]] |
| [[Crouching]] | [[Linked Slot]] | [[Equipped]] | [[Check Data]] | [[Entity Type]] |
| [[Soul Condition]] | [[WG Condition]] | [[Time]] | [[Biome]] | [[RPGCore Type]] |
| [[Phase]] | | | | |

# Configuration of Conditions

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| inverted | boolean | inverts the result of the condition | false | no | no |
| scale-off-parent | boolean | replaces the asker with the parent of the behaviour | false | no | no |