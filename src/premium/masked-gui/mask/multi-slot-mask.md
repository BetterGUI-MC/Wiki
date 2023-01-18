# Multi-Slot Mask

It's the same as the [Simple Mask](./simple-mask.md) but there is a special feature when you add multiple [Buttons](../../../Button.md).

## Format

```yaml
mask-name:
  mask: multislot
  slot: <slot>
  child:
    button-name-1:
      <button-settings>
    button-name-2:
      <button-settings>
    ...
```

## Example

```yaml
demo-slot:
  mask: multislot
  slot: 1-1-9-6
  child:
    emerald-button:
      id: emerald
      name: "&a&lEmerald"
```

![MultiSlot 1](images/multislot-1.png)

```yaml
demo-slot:
  mask: multislot
  slot: 1-1-9-6
  child:
    emerald-button:
      id: emerald
      name: "&a&lEmerald"
    diamond-button:
      id: diamond
      name: "&b&lDiamond"
```

![MultiSlot 2](images/multislot-2.png)

```yaml
demo-slot:
  mask: multislot
  slot: 1-1-9-6
  child:
    emerald-button:
      id: emerald
      name: "&a&lEmerald"
    diamond-button:
      id: diamond
      name: "&b&lDiamond"
    redstone-button:
      id: redstone
      name: "&c&lRedstone"
```

![MultiSlot 3](images/multislot-3.png)

You may now understand what is the special feature of this mask. This mask will loop through the [`child` buttons](../../../Button.md) and display them for each slot in the `slot` section.