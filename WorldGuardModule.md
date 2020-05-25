Directory: "./../WorldGuardModule.yml"  
Module: WorldGuardModule
Download: https://www.spigotmc.org/resources/67202/

A module for worldguard integration, you may define "PVP" and "PVE" flags to prevent damage interactions. You may define "TRIGGER" to skills from being used. You may define a "RPGCORE" flag and set it to the zone, making all entities in it enjoy certain attribute changes.

# General configuration

| Option | Type | Description |
|-|-|-|
| flush-interval | integer | interval at which we update the zone an entity belongs to |
| zone config | section | configurations for certain worldguard zones |

# Configuring a worldguard zone 

Note that while players check in which zone they are currently, mobs only check which zone they had spawned in (making their effect permanent!)

| Option | Type | Description |
|-|-|-|
| skill-list | skill list | list of skills to acquire while inside |
| effects | attribute modifiers | entity attributes enjoyed while inside |
| target-player | boolean | members can be players |
| target-non-player | boolean | members can be mobs |
| skill-level | integer | level of the acquired skills |
