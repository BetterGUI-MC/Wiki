# Info
* Requirement is one of the interesting parts of the plugin.
* It is used when you want to check if the player meets some sort of requirements before doing anything (Check the level before opening the menu, etc).
* There are many types of requirements, which will be listed below. A developer can also make his own requirement type and register it to the plugin.
# Type of Requirement
## Cooldown
* **The format**
```yaml
cooldown: <seconds>
```
* This requirement will check if the player is not in a cooldown timer. After checking successfully, the cooldown timer will start for the player.
* An example for this can be found in the example menu: [Here](https://github.com/BetterGUI-MC/BetterGUI/blob/17209a29e6b9948fd15991916a25a42763a68c6a/src/main/resources/menu/example.yml#L216)
## Condition
* **The format**
```yaml
condition: <condition>
```
```yaml
condition:
- <condition>
- <condition>
- <condition>
...
```
* This requirement will check if the player meets some certain `<condition>`
* An example for this can be found in the example menu: [Here](https://github.com/BetterGUI-MC/BetterGUI/blob/17209a29e6b9948fd15991916a25a42763a68c6a/src/main/resources/menu/example.yml#L281)
## Level
* **The format**
```yaml
level: <level>
```
```yaml
level:
  value: <level>
  take: <true/false>
```
* This requirement will check if the level of the player is higher or equal to the `<level>`
* You can specify the `take` value (`true` or `false`) to allow/disallow the plugin to take the level of the player alter checking successfully
* An example for this can be found in the example menu: [Here](https://github.com/BetterGUI-MC/BetterGUI/blob/17209a29e6b9948fd15991916a25a42763a68c6a/src/main/resources/menu/example.yml#L307)
## Permission
* **The format**
```yaml
permission: <permission>
```
```yaml
permission:
- <permission>
- <permission>
- <permission>
...
```
* This requirement will check if the player has the `<permission>`
* You can add `-` before `<permission>` to indicate that the plugin should check if the player doesn't have the `<permission>`
* An example for this can be found in the example menu: [Here](https://github.com/BetterGUI-MC/BetterGUI/blob/17209a29e6b9948fd15991916a25a42763a68c6a/src/main/resources/menu/example.yml#L150)