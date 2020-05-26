Directory: "./../skillmodule/skills"  
Module: SkillModule

Targetters re-map the original input from the trigger to a specific target. The original target differes from trigger to trigger, for example "deal-damage" would point at who you damaged while "timer" would just point at yourself.

# Available Targetters

| | | | | |
|-|-|-|-|-|
| [[default]] | [[flatten]] | [[inverted]] | [[facing]] | [[layered]] |
| [[nearby]] | [[offset]] | [[self]] | [[grounded]] | [[looking]] |
| [[distinct]] | [[limit]] | [[remember]] | [[forward]] | [[eyeheight]] |
| [[memorize]] | [[parent]] | [[random]] | [[signalled]] | [[exact]] |
| [[players]] | [[summoner]] | [[direction]] | [[rotate]] | |

# Configuration of Targetters

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| remember | string | will store the target to be accessible within the isolated execution | | no | no |
| conditions | string list | exact name of conditions defined by the parent skill | | no | no |