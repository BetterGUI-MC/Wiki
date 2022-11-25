# Permission Executor

## Format
* `permission: <permission> <command>`
* `permission: <permission_1>;<permission_2>;<permission_3> <command>`

## Description
This action will give the `<permission>` to the player, execute the `<command>` and then retrieve the `<permission>`

## Example
* `permission: essentials.fly fly`
* `permission: essentials.gamemode;essentials.gamemode.creative gamemode 1`

## Note
This is a safe way to execute the commands that require a specific permission, without touching the `/op` command