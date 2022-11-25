# Predicate Button

## Format
```yaml
button-name:
  type: predicate # aliases: requirement
  button:
    <button-settings>
  fallback:
    <button-settings>
  view-requirement:
    <requirement-set>
    <requirement-set>
    <requirement-set>
    ...
  check-only-on-creation: <true/false>
  click-requirement:
    left:
      <requirement-set>
      <requirement-set>
      <requirement-set>
      ...
    right:
      <requirement-set>
      <requirement-set>
      <requirement-set>
      ...
    middle:
      <requirement-set>
      <requirement-set>
      <requirement-set>
      ...
    ...
    default:
      <requirement-set>
      <requirement-set>
      <requirement-set>
      ...
```

## Description
* This button will show the [`button`](../Button.md) if only the player meets the [`view-requirement`](../Requirement-Set.md), Otherwise the [`fallback`](../Button.md) button will be shown.
* You can set the [`click-requirement`](../Requirement-Set.md) value if you want the plugin to check requirements when the player clicks the button.
* You can set the `check-only-on-creation` value to make the button only check [`view-requirement`](../Requirement-Set.md) when the player opens the menu.

## Example
```yaml
permission:
  SLOT: 1
  type: predicate
  CLICK-REQUIREMENT:
    default:
      permission:
        PERMISSION: bettergui.test
        fail-command: 'tell: &cYou don''t have the correct permission!'
  button:
    COMMAND: 'tell: &a[v] You have the correct permission!'
    NAME: '&8Permission test'
    LORE:
      - 'To use this item, you need the'
      - 'permission "bettergui.test".'
      - 'Otherwise, a configurable error'
      - 'message will be displayed.'
    ID: iron bars
```

```yaml
level-view-requirement:
  type: predicate
  slot: 2
  button:
    id: exp_bottle
    name: "&cA exp bottle"
    lore:
      - "You will see this icon when the level is higher than 5"
  fallback:
    id: stone
    name: "&cA stone"
    lore:
      - "You will see this icon when the level is lower than 5"
  view-requirement:
    level:
      level: 5
```