Directory: "./../Skills"  
Module: Skills

Mechanics refer to something that will be applied at the given target. This ranges from dealing damage to spawning particles and everything of similar nature. A lot of mechanics can interact with variables in one way or another, allowing for advanced logic behind them.

# Available Mechanics

| | | | | |
|-|-|-|-|-|
| [[Attachment]] | [[Cooldown]] | [[Damage]] | [[Modify Damage]] | [[Blocking Power]] |
| [[Multi Mechanic]] | [[Fake Block]] | [[Particle]] | [[Sound]] | [[Strike Thunder]] |
| [[Proxy]] | [[Armorstand]] | [[Use Command]] | [[Random Pick]] | [[MC Projectile]] |
| [[Potion]] | [[Ignite]] | [[Update Flag]] | [[Memorize Target]] | [[Modify Resource]] |
| [[Velocity]] | [[Abort Execution]] | [[Leap]] | [[Teleport]] | [[Trail]] |
| [[Upwind]] | [[Modify Support]] | [[Modify Data]] | [[Banner]] | [[Modify Minion]] |
| [[Summon]] | [[Taunt]] | [[Pathfinder]] | [[AI Target]] | [[Chatting]] |
| [[Modify Soul]] | [[Poison]] | [[Set Block]] | [[Suspend]] | [[Phase]] |
| [[Immortal]] | [[Interrupt]] | | | |



# Configuration of Mechanics

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| repeat | integer | how often to repeat mechanic | 1 | no | yes |
| interval | integer | repeat interval | 1 | no | yes |
| delay | integer | ticks to delay inital execution | 0 | no | yes |
| repeat-per-tick | integer | repeats multiple times in one tick | 1 | no | yes |
| | | | | | |
| cooldown | integer | cooldown in ticks for mechanic | 0 | no | yes |
| cooldown-id | string | the cooldown id used, is shared by all other cooldown systems | unique | no | no |
| | | | | | |
| mark | string | the jump mark (that may be jumped at from somewhere else) | / | no | no |
| jump | string | a jump mark that we wish to jump towards | / | no | no |
| maxjumps | integer | how often can this jump repeat | 1 | no | yes |
| | | | | | |
| chance | percent | execution chance | 100% | no | yes |
| cache-targets | boolean | cache targets when repeating | true | no | no |
| need-caster | boolean | keep executing when caster is dead/offline | false | no | no |
| conditions | condition list | a [[layered]] targetter, original input are targets | none | no | no |