Directory: "./../skillmodule/skills"  
Module: SkillModule

A trigger refers to a certain happening that matches out requirements for it, when a trigger is procced the logic of it will be executed.

# Configuration of Triggers

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| chance | percent | chance for the trigger to proc | 100% | no | yes |
| conditions | condition list | treated like a layered targetter, no targets remaining = dont trigger | | no | no |
| cooldown | integer | ticks to enter a cooldown after triggering | 0 | no | yes |
| priority | integer | lower priority is run first | 0 | no | no |
| cooldown-id | string | coodown namespace to share | random | no | no |

# Available Triggers


