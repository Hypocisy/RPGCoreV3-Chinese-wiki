Directory: "./../CraftDamageLoggerModule.yml"  
Module: CraftDamageLoggerModule

Prints damage output to the player chat, if you hover the message you can check on additional details of it. Damage that has the "DURATION" tag will not be logged. Will not document damage without an attacker or self mutilation damage.

# Configuring Damage Logger

| Option | Type | Description |
|-|-|-|
| pool-rate-dealt | integer | updating frequency, higher = better performance | 20 |
| pool-rate-taken | integer | updating frequency, higher - better performance | 5 |