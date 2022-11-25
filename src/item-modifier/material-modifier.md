# Material Modifier

## Format
```yaml
material: <material>
id: <material>
mat: <material>
raw-material: <material>
raw-id: <material>
raw-mat: <material>
```

## Description
* This modifier will set the `<material>` of the item
* You can set multiple materials as a list for the plugin to check for one available material. This helps Setup Makers to support both old and new version of the material

## Example
```yaml
stone-button:
  slot: 1
  id: stone
```
```yaml
player-head:
  slot: 2
  id:
  - player_head
  - skull_item:3
```

## Note
* [List of Materials](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html)