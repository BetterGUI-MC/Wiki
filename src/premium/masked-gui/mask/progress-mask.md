# Progress Mask

It is a mask that shows the progress of the player. It is useful for showing the progress of the player in a quest or a game.

## Format

```yaml
mask-name:
  mask: progress
  slot: <slot>
  current: <current-value>
  max: <max-value>
  current-button:
    <button-settings>
  max-button:
    <button-settings>
```

## Example

```yaml
demo-slot:
  mask: progress
  current: "{level}"
  max: 45
  slot: 1-1-9-5
  current-button:
    id: green_stained_glass_pane
    name: "&a&lCurrent: &e{level}"
  max-button:
    id: red_stained_glass_pane
    name: "&c&lMax: &e45"
```

![Progress 1](images/progress-1.gif)

Don't worry about the weird last row. I'll explain it later.
