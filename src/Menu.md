# Info
* Menus are what BetterGUI is for. It's the thing displayed to the player.
* There are many types of Menu. A developer can also make his own menu and register to the plugin.
* Generally, a menu contains 2 sections: `menu-settings` and [`Button`](https://github.com/BetterGUI-MC/BetterGUI/wiki/Button)
* You can set the type of menu by setting the `menu-type` value in the `menu-settings` section
# Type of Menus
## Simple Menu
* **The format**
```yaml
menu-settings:
  menu-type: simple # You don't need to set this type. It's the default value

  # The actions when the player opens the menu
  open-action:
  - action
  - action
  - action
  ...

  # The actions when the player closes the menu
  close-action:
  - action
  - action
  - action
  ...

  # The type of the display inventory
  # https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/inventory/InventoryType.html
  inventory-type: <inventory-type>
  #inventory: <inventory-type>

  # The rows <1-6> of the inventory if the type is CHEST
  rows: <1-6>
  
  # How frequently the menu will refresh itself
  auto-refresh: <ticks>
  #ticks: <ticks>

  # The requirement before the player can open the menu
  view-requirement:
    <requirement-set>
    <requirement-set>
    <requirement-set>
    ...

  # The requirement before the player can close the menu
  close-requirement:
    <requirement-set>
    <requirement-set>
    <requirement-set>
    ...

  # The permission required to open the menu
  permission: bettergui.test
  
  # The command to open the menu
  command:
  - command1
  - command2
  ...
  
  # The title of the inventory
  title: <name>
  #name: <name>

# This is a special button. It will fill all empty slots of the inventory (You don't need to set this button)
default-button:
  <button-settings>

button1:
  <button-settings>
button2:
  <button-settings>
...
```
* None of the `menu-settings` is required to get the menu working.
* The `open-action` and `close-action` use the [Action](https://github.com/BetterGUI-MC/BetterGUI/wiki/Action) value.
* The `view-requirement` and `close-requirement` use the [Requirement Set](https://github.com/BetterGUI-MC/BetterGUI/wiki/Requirement-Set) value.
* An example for this can be found [Here](https://github.com/BetterGUI-MC/BetterGUI/blob/master/src/main/resources/menu/example.yml)
## Args Menu
* Args Menu is the same as Simple Menu, with 4 more sections in the `menu-settings`
  * `min-args` sets the minimum amount of arguments in the command to open the menu
  * `args` sets the arguments
  * `min-args-action` sets the [Action](https://github.com/BetterGUI-MC/BetterGUI/wiki/Action) when the number of arguments is lower than `min-args`
  * `default-args` sets the default arguments
* **The format**
```yaml
menu-settings:
  menu-type: args
  min-args: <number>
  args:
  - arg1
  - arg2
  - arg3
  ...
  min-args-action:
  - action
  - action
  - action
  ...
  default-args: "string with space"
  <other-settings>

button1:
  <button-settings>
button2:
  <button-settings>
...
```
* When using this menu, the menu will register some [Variables](https://github.com/BetterGUI-MC/BetterGUI/wiki/Variable) to the plugin:
  * `{menu_<menu-name>_merged_args}` returns the completed arguments that the player typed to open the menu `<menu-name>`
  * `{menu_<menu-name>_arg_<arg>}` returns the value of the argument at the `<arg>` position from the menu `<menu-name>`
* Example:
```yaml
# Replace <menu-name> with your menu name
menu-settings:
  menu-type: args

  # The minimum number of arguments is 2
  min-args: 2

  # Register 2 arguments and register 2 variables to the plugin: {menu_<menu-name>_arg_test} and {menu_<menu-name>_arg_otest}
  args:
  - test
  - otest
  
  # Set the default arguments of "test" and "otest" to "hello" and "world"
  default-args: "hello world"
  
  # The action when failed to meet the min-args
  min-args-action: "tell: &cAt least 2 arguments"
  ...

# The button
button:
  id: stone
  name: "&bTest Arguments"
  lore:
  - "Arg 1: {menu_<menu-name>_arg_test}"
  - "Arg 2: {menu_<menu-name>_arg_otest}"
  - "Merged Args: {menu_<menu-name>_merged_args}"
``` 