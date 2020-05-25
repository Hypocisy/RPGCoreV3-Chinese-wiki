Directory: "./../itemmodule/items"  
Module: ItemModule

Materials refer to items which are designed to modify other items. Should you intend to use the [[MarketplaceModule]] you also can use them as the currency to exchange items with. Make sure to check the [[ItemModule: Items]] article too, this is just an extension of that article.

One material may only have one upgrade purpose, defining multiple purposes will have no effects on it. **Everything below is expected as an NBT tag.**

### General material configurations

| Option | Type | Description |
|-|-|-|
| success-chance | percentage | a chance for the upgrade to succeed (100% by default) |
| can-break-item | boolean | upgrade failure may cause the item to break (false by default) |

### Raise the upgrade tier

Upgrade tier will target one random modifier on the item to rise it by a single increment. This only affects modifiers that have a range by default (iE if only a static amount is offered it cannot be incremented.)

| Keyword | Type | Description |
|-|-|-|
| upgrade-minimum | integer | minimum tier to which the item has been upgraded before (inclusive) |
| upgrade-maximum | integer | maximum tier to which the item has been upgraded before (exclusive) |
| overcap-chance | percent | chance to upgrade beyond the limit of the range |
| upgrade-modifier-range | string list | which modifier ranges to upgrade |
randomize-modifier-range

### Randomizing Modifiers

Randomizes all targetted modifiers, note that overcapped modifiers will become capped from this - but the upgrading level is kept.

| Keyword | Type | Description |
|-|-|-|
| randomize-modifier-range | string list | modifiers which should be randomized |

### Levelling up Skills

Adds experience to the skill containers items, if they hit the experience threshold the skill will level up.

| Keyword | Type | Description |
|-|-|-|
| must-be-unused-skill | boolean | allows only to level skills which werent used before |
| skil-exp-to-add | integer | amount of exp to add to the skill |
| skill-upgrade-minimum-level | integer | minimum level which the skill has to be levelled to before (inclusive) |
| skill-upgrade-maximum-level | integer | maximum level which the skill has to be levelled to before (exclusive) |
| skill-exp-to-add | integer | positive number will add exp, negative number will add levels. |

### Rolling Additional Affixes

If the item has space for more affixes, we will attempt to roll one. You cannot roll the same affix type twice. Will require the item to have an affix pool specified. If you are lacking slots or compatible affixes, this may not work.

| Keyword | Type | Description |
|-|-|-|
| affixing-fortune | percentage | fortune when picking an affix |
| affix-tier-minimum | integer | threshold of affix tier rolled |
| affix-tier-maximum | integer | threshold of affix tier rolled |

### Re-Rolling Skill Links

Re-roll the skill link, picking one of the outcomes which are specified by the server. Fortune will re-roll the outcome and pick the rarest outcome.

| Keyword | Type | Description |
|-|-|-|
| link-roll-fortune | percentage | fortune when picking the outcome |

### Re-Rolling Skill Colors

Re-roll the colors of an item, this can affect socketables and skills. The coloring is weight locked, white colors are universally compatible.

| Keyword | Type | Description |
|-|-|-|
| coloring-target | SOCKET/SKILL | Re-roll the coloring for socketables or for skills. |



