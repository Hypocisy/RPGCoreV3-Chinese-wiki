Directory: "./../levelmodule.yml"  
Module: LevelModule, PassiveTreeModule, EntityModule

Killing mobs means you level up. Besides killing mobs, you also can receive experience from commands. Not to be confused with entity experience, skills also can gain experience and level up by gathering sufficient amounts of experience. 

# Level scaling experience

Control the scaling of experience based on level difference, this applies both of PvP and PvE - the difference is relative from killer to killed. 

The closest value will be used, so if you only setup something for 10 levels but have a difference of 15 levels we will use the setting for 10 levels. Special care is recommended with PvP scaling, as the experience dropped is relative to the remaining experience of the player.

In the default configuration, the death of a Lv120 player will reward 250.000 experience points. Hence, forcing pvp rewards to be in similar level ranges is recommended (or just removing any experience from pvp rewards.)

| Option | Type | Description |
|-|-|-|
| exp-multiplier-level-difference-pve | section | multiplier for PvE level difference |
| exp-multiplier-level-difference-pvp | section | multiplier for PvP level difference |

# Configuring levels

Every level requires a customized configuration. The keying is the level we are processing, make sure that you do not keep any gaps between the levels so players can actually level up. Players start at Lv1.

| Option | Type | Description |
|-|-|-|
| experience | integer | experience to level up |
| name-prefix | string | adds a prefix to the name of a player |
| name-suffix | string | adds a suffix to the name of a player |
| passive-tree | section | passive point type mapped to reward |
| death-kill-logic.player-death-penalty | percent | experience lost, cannot drop a level |
| death-kill-logic.pvp-experience-reward | percent | experience lost given to pvp killer |
| notification-self | string list | message sent to player, {0} is reached level |
| notification-global | string list | message broadcasted, {0} is name, {1} is level |
| bottleneck | section | stop from levelling up, until a command is run to break the bottleneck |

# Bottlenecks

Bottlenecks are an excellent way to guide and limit progression, a bottleneck can be broken by running the "rc bottleneck <id>" command. While a player is stuck at a bottleneck, they cannot gain any skill experience.