Directory: "./../TitleModule.yml"  
Module: TitleModule

Titles are managed with their commands, you can see them listed when you run the "rc help" command. A player can have a number of passive titles, and one main title. The only effect of titles are attributes, the implementation is fairly efficient so even having thousands of titles should be blazing fast - provided you are using specific numbers in their effects.

The [[CraftEntityHoloTagModule]] also happens to display the main title of a player!

Please note that titles are per character, they are not shared across characters.

# General configuration

Make sure that the active and inactive title have the identical name, otherwise they are considered two different titles! You only gain one effect a time, so if you have a title as the active one you will not get the inactive effects of it.

| Option | Type | Description |
|-|-|-|
| active-title-option | section | a title mapped to the attribute effects of it |
| inactive-title-option | section | a title mapped to the inactive effects of it |