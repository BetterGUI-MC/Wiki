# Air Button

## Format
```yaml
button-name:
  type: air
  # command:
  action:
  - <action>
  - <action>
  - <action>
  ...
  close-on-click: <true/false>
```

## Description
* This button represents the Air item, which the player can't see.
* You can only set two settings: [`action` (`command`)](../Action.md) and `close-on-click`

## Example
```yaml
air-button:
  type: air
  command:
  - "tell: &aOh..."
  - "delay: 30"
  - "tell: &aUhhhh... Hello"
  close-on-click: true
```