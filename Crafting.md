Directory: "./../Crafting.yml"  
Module: Crafting

This module permits you to left click on an item while holding a certain [[ItemModule: Materials]] to modify the said item.

# Applying Held Item

Apply an item you are holding in your hand.

| Option | Type | Description |
|-|-|-|
| incompatible-material | string | material cannot be applied |
| successful-applied | string | application was successful |
| failure-applied | string | application has failed |
| item-broken | string | application and breaking roll failed |
| item-protected | string | was meant to break, but was protected |
| chance-to-break-on-fail | percent | chance for the upgrade to break the item |
# Melting Items

Melt an item, usually done with a melting station. Rewards are configured per-item.

| Option | Type | Description |
|-|-|-|
| messages | section | a section of messages |
| use-anvils-to-craft | location list | location of all anvils that can be used |
| breakdown-rules | section | the score parameters controlling reward count |

# Crafting Station

Rapidly apply materials on a target item.

| Option | Type | Description |
|-|-|-|
| messages | section | a section of messages |
| use-anvils-to-craft | location list | location of all anvils that can be used |
| chance-to-break-on-fail | percent | chance for apply failure to break the item |