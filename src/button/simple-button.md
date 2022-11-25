# Simple Button

## Format
```yaml
button-name:
  type: simple # You don't need to set this value. It's the default value
  modifier1: <value1>
  modifier2: <value2>
  modifier3: <value3>
  ...
  # command:
  action:
  - <action>
  - <action>
  - <action>
  ...
  close-on-click: <true/false>
```

## Description
* This is a combination of [Dummy Button](dummy-button.md) and [Air Button](air-button.md)
* You can set the display item through [Item Modifiers](../Item-Modifier.md), and also set the 2 settings: [`action` (`command`)](../Action.md) and `close-on-click`

## Example
```yaml
simple-button:
  id: cobblestone
  name: "&bThis is a simple button"
  lore:
  - ""
  - "&fThis is a lore"
  action: "tell: &eYou clicked"
  close-on-click: true
```