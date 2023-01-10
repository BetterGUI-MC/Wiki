# ItemBridge Hook
> [Code](https://github.com/BetterGUI-MC/ItemBridgeHook) | [Download](https://ci.codemc.io/job/BetterGUI-MC/view/Addon/job/ItemBridgeHook/)
 
> Depend: [ItemBridge](https://www.spigotmc.org/resources/itembridge-save-items-and-use-them-wherever-you-want-including-other-plugins-best-w-customitems.77080/)

## Format

```yaml
itembridge: <id>
item-bridge: <id>
```

## Description

This item modifier allows you to use the item with the `<id>` from [ItemBridge](https://www.spigotmc.org/resources/itembridge-save-items-and-use-them-wherever-you-want-including-other-plugins-best-w-customitems.77080/) in your menus.

## Note

This item modifier is order-sensitive. You have to set it before other modifiers.

## Example

```yaml
test-itembridge:
  slot: 0
  itembridge: "minecraft:stone"
  name: "&bItemBridge"
```