Directory: "./../Skillbar.yml", "./../Skills/"  
Module: Skillbar, Skills

The skillbar fixedly occupies the 2nd to 6th slot on the hotbar. You can cast skills by tapping on the respective key, you may need to spend a bit of time actually casting the ability. Other players should be unable to see you swap your inventory. Swap pages by hitting the F key. The skillbar works pretty well for every playstyle. Besides self-casting you can also place traps or summon totems.

# Skill configuration

You must setup a skill so that it can show up on your skillbar. The things shown are triggers, specifically: [[Totem]], [[Trap]] and [[Cast]] - You can find samples of these in the default configurations. The skills should be usable from any source of your picking.

# General configuration

| Option | Type | Description |
|-|-|-|
| totem-prefix | string | words before a totem their name |
| totem-suffix | string | words after a totem their name |
| maximum-skill-pages | integer | 4 skills per page, scroll with f |
| default-gcd | integer | silently block skillbar usage |
| empty-slot | string list | name followed by lore for empty skill |
| info-??-cast | string list | name followed by lore for style explanation |
| cooldown-pattern | string | formats cooldown to a certain pattern (no gcd) |
| not-enough-??-pattern | string | message for lacking resources |
| warn-for-channeling | string | warning to crouch to channel |
| warn-too-many-?? | string | warning exceeding maximum totems/traps |
| chest-gui-title | string | title of the chest-gui |