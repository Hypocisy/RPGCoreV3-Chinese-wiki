Directory: "./../Skills"  
Module: Skills

A trigger refers to a certain happening that matches out requirements for it, when a trigger is procced the logic of it will be executed.

# Available Triggers

| | | | | |
|-|-|-|-|-|
| [[Command]] | [[Move]] | [[Take Damage]] | [[Deal Damage]] | [[Signal]] |
| [[Timer Sync]] | [[Timer Async]] | [[Death]] | [[Kill]] | [[Interact]] |
| [[Cast]] | [[Trap]] | [[Totem]] | [[Shoot]] | [[Arrow Hit]] |
| [[Arrow Forked]] | [[Arrow Chained]] | [[Arrow Pierced]] | [[Sprint]] | [[Crouch]] |
| [[Dummy]] | [[Flag]] | [[Summoned]] | [[Consumable]] | [[Behaviour]] |
| [[Looting]] | [[Pathfinder]] | | | |

# Configuration of Triggers

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| chance | percent | chance for the trigger to proc | 100% | no | yes |
| conditions | condition list | treated like a layered targetter, no targets remaining = dont trigger | | no | no |
| cooldown | integer | ticks to enter a cooldown after triggering | 0 | no | yes |
| priority | integer | lower priority is run first | 0 | no | no |
| cooldown-id | string | coodown namespace to share | random | no | no |
| phase | string list | a phase requirement iE 'SHIELD_PHASE:PREPARING' checks for 'PREPARING' as the value of 'SHIELD_PHASE' - all of these phases must be matching. | | no | no |
| condition | decimal | the final result is checked with boolean logic, full access to variables | 1 | no | yes |


