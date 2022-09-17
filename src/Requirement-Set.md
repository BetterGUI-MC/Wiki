# Info
* A requirement set is a set of requirements that the player are required to pass.
* It consists of:
  * The [Requirements](https://github.com/BetterGUI-MC/BetterGUI/wiki/Requirement)
  * The [`success-command`](https://github.com/BetterGUI-MC/BetterGUI/wiki/Action) when the player passes all requirements
  * The [`fail-command`](https://github.com/BetterGUI-MC/BetterGUI/wiki/Action) when the player doesn't pass any of the requirements (rarely used)
# Example
```yaml
nether_world: # The requirement set's name
  condition: STREQ("{world}", "world_nether") # The condition requirement
  level: 10 # The level requirement
  success-command: # Actions when the player passes the requirements
  - "tell: &aYou are in nether"
```