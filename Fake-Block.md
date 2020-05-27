Sends a block change to targetted players, note that the change is packet based. A player may end up glitching should you change the type of a block. If we got some sort of data on the block, it should be retained.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | string | / | fakeblock | / | / |
| duration | ticks | how long before sending the actual block to the player again | | no | yes |
| material-distribution | section or string | section like {mat0:weight0m...} or string like "mat0:weight0,mat1:weight1,..." | | yes | no |
