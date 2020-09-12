Directory: "./../Skills"  
Module: Skills

Skills refer to a number of behaviours. A behaviour is made up of a trigger (Telling when something should happen) and a list of actions (Telling what should happen to who.) The system is extremely powerful once you get a good grip on it. An example definition is "When a player takes damage, all their allies should recover health."

# General Skill Configuration

The general configuration of a skill.

| Key | Type | Description |
|-|-|-|-|-|-|
| id | string | unique id of the skill |
| enchant | section | [[Items: Enchantments]] configuration |
| name | string | displayname of the skill |
| lore | string list | description of the skill |
| level-scaling | string list | tags that can scale the level (player level requirement unaffected) |
| variable-register | section | variables that can be read up by the skill, useless on their own |
| behaviours | section | behaviours defining the skill |
| targetters | section | if you need to define complex targetters |
| requirement-configuration | integer list | level requirement for players, unaffected by extra levels |
| level-configuration | integer list | experience to level up to the next skill level |

# Components of skills

| | | |
|-|-|-|
| [[Skills: Behaviours]] | [[Skills: Triggers]] | [[Skills: Mechanics]] |
| [[Skills: Targetters]] | [[Skills: Conditions]] | [[Skills: Itemization]] |
| [[Skills: Effect Cluster]] | [[Skills: Levelling]] | [[Skills: Variables]] |