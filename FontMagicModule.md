Directory: "./../FontMagicActionBarModule.yml"  
Module: FontMagicActionBarModule

A module using some font tricks available after 1.13 to create some custom interface elements. Should you be on 1.12 there are a number of fallback systems in place, but you are rather limited.

# General configuration

Beware that you will need to dig deeper into the fonts if you want to modify the parameters here. Should you end up breaking something. This does not only refer to configuration, but also the know-how for how to modify fonts. 

| Option | Type | Description |
|-|-|-|
| legacy-style | boolean | legacy style, forced on minecraft 1.12 |
| show-full-number | boolean | shows remaining and maximum alike |
| soul-characters | character list | characters representing filling state of souls |
| duration-characters | character list | duration overlay for status effect icons |
| character-table.fallback | character | fallback for status effect icons |
| character-table.effects.named-effects | section | named behaviours mapped to characters for status effects |
| character-table.bridge | character | character for the background bridge |
| character-table.overlay-left | character | character for the left overlay |
| character-table.overlay-right | character | character for the right overlay | 
| character-table.health | section | characters for all states |
| character-table.shield | section | characters for all states |
| character-table.mana | section | characters for all states |

# Configuring font constants

These values are (mostly) results of trial and error. If you change one value, you are expected to tinker around until you find the proper values yourself. Do not expect me to help you figuring the numbers out.

| Option | Type | Description | Defaults |
|-|-|-|-|
| constants.length-life | integer | how many symbols to display life (and shield) | 30 |
| constants.length-mana | integer | how many symbols to display mana | 30 |
| constants.shield-health-ratio | decimal | maximum 1.0, health covered by shield | 0.7 |
| constants.width-segment | integer | width of one segment of health/mana/shield (must be uniform) | 4 |
| constants.width-sides | integer | width of the side pieces of a bar | 32 |
| constants.width-bridge | integer | width of the bridge between two bars | 48 |
| constants.width-status | integer | width of a status effect symbol | 16 |
| constants.status-font-shift | integer | offset for the normal characters used by status effects | 0xEF00 |
| constants.bar-font-shift | integer | offset for the normal characters used by the bars | 0x2F00 |
| constants.overlay-shift | integer | correction shifting for the overlays | 351 |
| constants.back-shift-correction | integer | correction shifting for overlays | 4 |