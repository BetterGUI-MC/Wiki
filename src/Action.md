# Info
* Actions are used when you want to execute something on certain events (broadcast everyone when the player clicked the button, etc).
* There are many types of actions. There will be listed in the sections below. A developer can also create his own action and register to this plugin.
# Type of Action
## Menu
### Back
* **The format**
  * `back-menu`
  * `backmenu`
* This action will send the player to his previous menu, or close the current menu if there is no previous menu
### Close
* **The format**
  * `close-menu`
  * `closemenu`
* This action will close the current menu
### Update
* **The format**
  * `update-menu`
  * `updatemenu`
* This action will execute the update task of the current menu
### Open
* **The format**
  * `open-menu: <menu_name>`
  * `open: <menu_name>`
  * `menu: <menu_name>`
* This action will open the menu named `<menu_name>`
* If you want to open the menu named `test.yml`, the correct action will be `open-menu: test.yml`, `open: test.yml` or `menu: test.yml`
## Executor
### Console
* **The format**
  * `console: <command>`
* This action will execute the command `<command>` as the console (terminal)
* An example for this can be found in the example menu: [Here](https://github.com/BetterGUI-MC/BetterGUI/blob/17209a29e6b9948fd15991916a25a42763a68c6a/src/main/resources/menu/example.yml#L77)
### Player
* **The format**
  * `<command>`
  * `player: <command>`
* This action will execute the command `<command>` as a player
* This is the default type of all actions, so you can specific the action without the prefix `player:`
* An example for this can be found in the example menu: [Here](https://github.com/BetterGUI-MC/BetterGUI/blob/17209a29e6b9948fd15991916a25a42763a68c6a/src/main/resources/menu/example.yml#L39)
### OP
* **The format**
  * `op: <command>`
* This action will execute the command `<command>` as an OP player
* This action will give the player OP `/op`, execute the `<command>` and then de-op the player
* Since it uses `/op`, this action is considered "dangerous". A hacker can use a Crasher to exploit the action
### Permission
* **The format**
  * `permission: <permission> <command>`
* This action will give the `<permission>` to the player, execute the `<command>` and then retrieve the `<permission>`
* This is a safe way to execute the commands that require a specific permission, without touching the `/op` command
* You know EssentialsX right? I love the `/fly` command of that plugin, but it requires me to have the permission `essentials.fly`. If you want to enable the fly function for the player, without using the `/op` command, here is the action you want: `permission: essentials.fly fly`
## Message
### Broadcast
* **The format**
  * `broadcast: <message>`
* This action will send the `<message>` to every online players
* This example action will send the message "Hello" to every online players: `broadcast: Hello`
### Tell
* **The format**
  * `tell: <message>`
* This action will send the `<message>` to the player
* An example for this can be found in the example menu: [Here](https://github.com/BetterGUI-MC/BetterGUI/blob/17209a29e6b9948fd15991916a25a42763a68c6a/src/main/resources/menu/example.yml#L124)
## Sound
### Music
* **The format**
  * `music: <sheet>`
* This will run the `<sheet>` and send the sound to the player
* This is a complicated action. The explanation on how to make a `<sheet>` can be found [here](https://github.com/CryptoMorin/XSeries/blob/ceff291550d50a413d9f50d71b95e690c3bfa94a/src/main/java/com/cryptomorin/xseries/NoteBlockMusic.java#L133-L178)
### Sound
* **The format**
  * `sound: <sound> [volume] [pitch]`
* This action will send the `<sound>` to the player
* You can specify the `[volume]` and the `[pitch]` of the `<sound>`. Those are optional
* The list of sounds: [Sounds](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Sound.html)
### Raw Sound
* **The format**
  * `raw-sound: <sound>, [volume], [pitch]`
* This action will send the `<sound>` to the player
* The `<sound>` uses the Minecraft sound's name, so it also supports custom sounds from Resource Pack. If the `<sound>` can not be found, the action is simply ignored
* You can specify the `[volume]` and the `[pitch]` of the `<sound>`. Those are optional
## Misc
### Condition
* **The format**
  * `condition: <condition>`
* The action will check if the player meets the `<condition>`. If he doesn't, the actions after this will be ignored.
* For example, this action will check if the level of the player is higher than 5: `condition: {level} > 5`
### Delay
* **The format**
  * `delay: <ticks>`
* This action will delay the action flow in `<ticks>` ticks (20 ticks = 1 second)
* An example for this can be found in the example menu: [Here](https://github.com/BetterGUI-MC/BetterGUI/blob/17209a29e6b9948fd15991916a25a42763a68c6a/src/main/resources/menu/example.yml#L195)