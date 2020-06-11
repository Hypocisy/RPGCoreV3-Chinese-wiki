Directory: "./../DefaultCharacterSelectionModule.yml"  
Module: DefaultCharacterSelectionModule

A module to let players pick their characters. Do **not** disable this if you want to remove characters, should you not want a character system just delete all character slots and rpgcore will bypass this selection.

Note that the player is still the same, changing the UUID of a player is not possible so third party plugins may raise unexpected issues.

# General configuration

| Option | Type | Description |
|-|-|-|
| secondary-authentication | boolean | only shows up after the "/rc character" command is run |
| fallback-location | location | "world x y z" to spawn character at |
| character-configuration | section | character slots to offer players |

# Configuring a character slot 

| Option | Type | Description |
|-|-|-|
| title | string | displayname of this character slot |
| permission | string | permission, if necessary, to use the slot |
| internal-identity | integer | id of this character slot |
| chest-gui-position | integer | position in the chest gui |
| icon-existing | material | icon when the slot has an existing character |
| icon-missing | material | icon when the slot has no existing character |