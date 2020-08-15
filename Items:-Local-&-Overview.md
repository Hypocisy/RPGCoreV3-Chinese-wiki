Directory: "./../Items/", "./../Attributes.yml"  
Module: Items, Attributes

RPGCore allows you to scale attributes that are specific to an item, hence when an item holds a certain local modifier it will multiply all **base** instances of that modifier. You cannot scale increases and multipliers with the local modifier.

The overview is simply attributes pinned to the top of an item, **only** base attributes may be pinned like this. The attributes pinned/overviewed like this will be already multiplied with local parameters.

Do not forget to create Language patterns for your custom attributes, so that they can actually be listed on the item.

# Creating a local modifier (./../Attributes.yml)

Note that this attribute **does not exist on runtime.** The only instance where this is present is when rpgcore updates the internal mappings of a player (iE: Equipping a different item) - multiplying all attributes that are matching the targets.

| Option | Type | Description |
|-|-|-|
| local-attributes | id-to-list | the entity attribute mapped to local attributes |

# Using overviews (./../Items/items/..)

Note that an overview is only generated if the base of all attribute instances present on the item equals 0.

| Option | Type | Description |
|-|-|-|
| attribute-overview | id-to-pattern | an attribute mapped to a pattern, will be pinned |

# Using local modifiers (./../Items/..)

There is no dedicated location where you add local modifiers, anywhere on an item that evaluates to an entity attribute can have it. Note that combat attributes are not entity attributes (Example: Implicits, Affixes are entity attributes. Melee modifiers are combat attributes.)

Every modifier on the item which matches the target attribute will be scaled, note that this applies as a magnitude (negative numbers become even more negative, positive numbers even more positive.) And while you cannot list the local modifier among combat attributes, the local modifier can still scale combat modifiers.

# Example Cases

Presuming the local modifier below

> LOCAL_LIGHTNING_MODIFIER: [RESISTANCE_LIGHTNING, PENETRATION_LIGHTNING, DOT_MULTIPLIER_LIGHTNING, DAMAGE_LIGHTNING]

You can use

>'ADD 0.5 TO LOCAL_LIGHTNING_MODIFIER'

As an entity attribute acquired by the item (Example: Implicit, Affix) when present on the item the relevant lightning modifiers on the item will be multiplied with 1.5x

>'ADD 0.58 TO RESISTANCE_LIGHTNING'

Would become 58% x 1.5 = 87% Lightning Resistance.