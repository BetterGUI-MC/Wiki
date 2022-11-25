# Args Menu

## Format
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

## Description
* Args Menu is the same as [Simple Menu](./simple-menu.md), with 4 more sections in the `menu-settings`
  * `min-args` sets the minimum amount of arguments in the command to open the menu
  * `args` sets the arguments
  * `min-args-action` sets the [Action](../Action.md) when the number of arguments is lower than `min-args`
  * `default-args` sets the default arguments

## Note
* When using this menu, the menu will create some [Variables](../Variable.md):
  * `{merged_args}` returns the completed arguments that the player typed to open the menu
  * `{arg_<arg>}` returns the value of the argument at the `<arg>` position from the menu

## Example
```yaml
menu-settings:
  menu-type: args

  # The minimum number of arguments is 2
  min-args: 2

  # Register 2 arguments and create 2 variables: {arg_test} and {arg_otest}
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
  - "Arg 1: {arg_test}"
  - "Arg 2: {arg_otest}"
  - "Merged Args: {merged_args}"
``` 