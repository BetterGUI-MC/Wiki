# MaskedGUI 

## Description

**MaskedGUI** is an addon for your existing menus. It introduces new advanced features to make more complex menus and allows for more possibilities, while keeping the same level of simplicity if you are familiar with **BetterGUI**.

Some possible menus you can make with this addon are:
- [A menu with a welcome animation](https://youtu.be/g6r73BCpMU4)
- [Frame-by-frame animation](https://youtu.be/9cmGYL6BTdY)
- [Progress bar](https://youtu.be/txd07psA3NM)
- [Pagination](https://youtu.be/iajNu8t9JnQ)
- _And more!_

## Get Started

After downloading, follow [this guide](../Basic-tutorial.md#add-an-addon) to install the addon.

To start using the addon in your menu, simply set `menu-type` of `menu-settings` to `masked`.

```yaml
menu-settings:
  menu-type: masked
  name: '&c&lExample Menu'
  rows: 6
  ...
```

## Mask

**Mask** is a new component in which you can specify the logic on how the [Buttons](../Button.md) are displayed. This creates new possibilities to make more creative menus from your crazy ideas.

You can use this to make a simple menu

<iframe width="560" height="315" src="https://www.youtube.com/embed/sJhsBfklfOE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

... or a more complex menu

<iframe width="560" height="315" src="https://www.youtube.com/embed/g6r73BCpMU4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

## Built-in Mask

* Simple Mask
* Multi-Slot Mask
* Pattern Mask
* Progress Mask
* Hybrid Mask
* Animated Mask
* One-Time Animated Mask
* Predicate Mask
* List Mask
* Button Paginated Mask
* Sequence Paginated Mask
* Mask Paginated Mask