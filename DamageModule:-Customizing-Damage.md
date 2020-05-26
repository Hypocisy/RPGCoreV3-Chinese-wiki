Directory: "./../DamageModule.yml"  
Module: DamageModule

Customizing the way damage works on your server is very much possible, to a more limited extent you also can interact with the things defined in [[DamageModule: Hardcoded Behaviour]] by directly modifying their combat attribute.

# How to modify the damage formula

Modifying the damage formula will require you to respect the syntax of [EvalEx](https://github.com/uklimaschewski/EvalEx), you may put the functions which are defined in it to use to create your own logic. When you define a variable in the formula, make sure to add it to the variables listed below too.

Damage is calculcated for each element individually, in the sequence defined by the damage elements. Should you require it, you may setup default values for the variable configurations.

| Option | Type | Description |
|-|-|-|
| damage-elements | element list | list of elements, damage is processed in sequence |
| variable-configurations | attribute modifiers | default attributes for damage, %ELEMENT% generates all permutations |
| damage-formula | formula | EvalEx formula for this specific element, result is damage output |
| damage-variables | string list | list of all variables added to formula |

# How to modify damage application

Damage application controls where which damage is applied. You may control which resource absorbs which damage type, in what sequence what type of damage is absorbed and how much of it is absorbed. Beware that only hitting 0 health will cause the death of an entity, hence the take from life should be the highest priority.

| Option | Type | Description |
|-|-|-|
| priority | integer | lowest priorities are processed first |
| damage-application.target | resource | Absorb from your health, shield or mana pool |
| damage-application.factor | decimal/attribute | a factor defining how much is absorbed |
| damage-application.elements | element list | list of elements which we can apply |
| damage-application.types | type list | list of types which we can apply |

# How to create custom damage computers

Damage computers are the interface between entity attributes and combat attributes, an example usage would be setting up simple percentage based damage reductions. But you can also setup more complex systems such as evasion-accuracy based on more complicated values.

| Option | Type | Description |
|-|-|-|
| elemental-types | element list | options for the %ELEMENT% variable to take up |
| damage-types | type list | options for the %TYPE% variable to take up, skips if missing damage type |
| variable | entity attribute | entity attribute to read from, created if missing |
| operations.write-target | combat attribute | combat attribute to write to |
| operations.write-operation | string | base, increased or multiplied operation|
| operations.from-attacker | boolean | read entity attribute from attacker or defender |
| operations.subtract | boolean | multiplies the result with -1 |
| operations.mask | EvalEx formula | applies some math before passing to combat attribute, where x=attribute |
