# Target Menu
> [Code](https://github.com/BetterGUI-MC/TargetMenu/) | [Download](https://ci.codemc.io/job/BetterGUI-MC/view/Addon/job/TargetMenu/)

## Format
```yaml
menu-settings:
  menu-type: target
  ...

...
```
```yaml
menu-settings:
  menu-type: target-args # To use settings from Args Menun
  ...

...
```

## Description
This is a variant of [Simple Menu](../menu/simple-menu.md) ([Args Menu](../menu/args-menu.md) if the `menu-type` is `target-args`) that supports specifying the target player to do actions with

## Note

### Target Variable
The menu will register 2 [Menu Variables](../Variable.md#menu-variables):
* `{target_<variable_name>}` to fetch the variable `<variable_name>` of the target player
  * Example:
    * `{player}` -> `{target_player}`
    * `{ping}` -> `{target_ping}`
    * `{exp_to_level}` -> `{target_exp_to_level}`
* `{target_papi_<placeholder_name>}` to fetch the PlaceholderAPI's placeholder `<placeholder_name>` of the target player

### Open Command
You can specify the target player to do actions with:
* In [open command](../Command-&-Permission.md): 
  * `/<menu_command> <target_player> [args]`
  * `/openmenu <menu_file> <player> <target_player> [args]`
* In [`open-menu` action](../action/open-menu.md):
  * `open: <menu_file> <target_player> [args]`