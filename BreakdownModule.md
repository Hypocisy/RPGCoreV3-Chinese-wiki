Directory: "./../ItemDamageModule.yml"  
Module: ItemDamageModule

This module allows you to melt down items you don't want, intended to reward you with materials in exchange. A "value" is generated for the item to be melted, defining how many items you would gain and how high their value would be.

# Configuring the module

Beneath is the configuration of the module, note that while we say anvil it can be any sort of block in its place. It is recommended to not change the attempt rule, as the default item configurations was specifically balanced around it with trial and error.

| Option | Type | Description |
|-|-|-|
| messages | section | messages shown for certain situations |
| use-anvils-to-breakdown | location list | list of locations where we can melt down items |
| breakdown-rules.attempt-rule | integer | an threshold controlling how many attempts players have |
| breakdown-rules.rarity-rule | section | breakdown score gained based on rarity |
| breakdown-rules.affix-rule | decimal | breakdown score gained per filled affix |
| breakdown-rules.jewel-rule | decimal | breakdown score gained per open jewel slot |
| breakdown-rules.skill-rule | decimal | breakdown score gained per open skill slot |
| breakdown-rules.upgrade-rule | decimal | breakdown score gained per upgrade level |

# How to make an item that can be melted

This is a part of the configuration of an item itself.

| Option | Type | Description |
|-|-|-|
| custom.tags.breakdown-score | integer | basic melt down score, defaults to -99999|

