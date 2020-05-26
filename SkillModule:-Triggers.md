Directory: "./../skillmodule/skills"  
Module: SkillModule

A trigger refers to a certain happening that matches out requirements for it, when a trigger is procced the logic of it will be executed.

# Available Triggers

| | | | | |
|-|-|-|-|-|
| [[Trigger: Command]] | [[Trigger: Move]] | [[Trigger: Take Damage]] | [[Trigger: Deal Damage]] | [[Trigger: Signal]] |
| [[Trigger: Timer Sync]] | [[Trigger: Timer Async]] | [[Trigger: Death]] | [[Trigger: Kill]] | [[Trigger: Interact]] |
| [[Trigger: Cast]] | [[Trigger: Trap]] | [[Trigger: Totem]] | [[Trigger: Shoot]] | [[Trigger: Arrow Hit]] |
| [[Trigger: Arrow Forked]] | [[Trigger: Arrow Chained]] | [[Trigger: Arrow Pierced]] | [[Trigger: Sprint]] | [[Trigger: Crouch]] |
| [[Trigger: Dummy]] | [[Trigger: Flag]] | [[Trigger: Summoned]] | [[Trigger: Consumable]] | [[Trigger: Behaviour]] |


# Configuration of Triggers

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| chance | percent | chance for the trigger to proc | 100% | no | yes |
| conditions | condition list | treated like a layered targetter, no targets remaining = dont trigger | | no | no |
| cooldown | integer | ticks to enter a cooldown after triggering | 0 | no | yes |
| priority | integer | lower priority is run first | 0 | no | no |
| cooldown-id | string | coodown namespace to share | random | no | no |



