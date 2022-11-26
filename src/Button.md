# Button

## Description
* A button is what is shown in the menu.
* When the player clicks a button, some actions are executed.
* A button can also be updated.
* There are many built-in types of button. A developer can make his own button and register to the plugin.
* You can specify the type of button by setting the `type` option. By default, it will take the value of `default-button-type` from `config.yml`

## Example
```yaml
simple-button: #
  slot: 1
  id: cobblestone
  name: "&bThis is a simple button"
  lore:
  - ""
  - "&fThis is a lore"
  action: "tell: &eYou clicked"
  close-on-click: true

animated-icon:
  slot: 2
  type: animated
  update: 5
  async: false
  child:
    frame_icon1:
      name: "&cFrame 1"
      id: red_wool
      lore:
        - "This is part of an animated icon"
    frame_icon2:
      name: "&aFrame 2"
      id: green_wool
      lore:
        - "This is part of an animated icon"
    frame_icon3:
      name: "&bFrame 3"
      id: light_blue_wool
      lore:
        - "This is part of an animated icon"
```

## Built-ins
* [Empty Button](./button/empty-button.md)
* [Dummy Button](./button/dummy-button.md)
* [Air Button](./button/air-button.md)
* [Null Button](./button/null-button.md)
* [Simple Button](./button/simple-button.md)
* [Animated Button](./button/animated-button.md)
* [Predicate Button](./button/predicate-button.md)
* [List Button](./button/list-button.md)
* [Template Button](./button/template-button.md)