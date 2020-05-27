Check the passed position for a certain material type. The following notation can be used: `should-be=0:STONE|GOLD_BLOCK,-1:WATER|AIR` where the number is the offset from the given position, and the accepted materials are separated with a | symbol.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | / | / | material | / | / |
| should-be | string list | if not empty will require the target to be listed here | | no | no |
| should-not-be | string list | if not empty will require the target to not be listed here | | no | no |