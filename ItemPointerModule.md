Directory: "./../ItemPointerModule.yml"  
Module: ItemPointerModule

A module to let item drops be indicated by glowing, helpful to show off high value items and add nametags floating above the item to make the purpose of it obvious.

You might need to delete the teams files from your server if you want to update the colors.

# General configuration

| Option | Type | Description |
|-|-|-|
| display-bindings | section | tags mappped to their display effect |
| glow-color | section | rarity mapped to glow color |

# Configuring an item for a custom binding

This is expected to be an NBT tag, if we have no display binding it will default to the item rarity.

| Option | Type | Description |
|-|-|-|
| display-binding | string | the binding to attach to the item |