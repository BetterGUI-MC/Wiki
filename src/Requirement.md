# Requirement

## Description
* Requirement is one of the interesting parts of the plugin.
* It is used when you want to check if the player meets some sort of requirements before doing anything (Check the level before opening the menu, etc).
* There are many built-in types of requirements, which will be listed below. A developer can also make his own requirement type and register it to the plugin.

## Example
```yaml
permission-list:
  slot: 1
  type: predicate
  CLICK-REQUIREMENT: # Click Requirement
    default: # Click type
      permission: # Requirement set name
        PERMISSION: # Here we are
        - bettergui.test
        - bettergui.test.1
        fail-command: 'tell: &cYou don''t have the correct permission!'
  button:
    COMMAND: 'tell: &a[v] You have the correct permission!'
    NAME: '&8Permission test'
    LORE:
      - 'To use this item, you need the'
      - 'required permissions.'
      - 'Otherwise, a configurable error'
      - 'message will be displayed.'
    ID: iron bars
```

## Built-ins
* [Cooldown Requirement](./requirement/cooldown-requirement.md)
* [Level Requirement](./requirement/level-requirement.md)
* [Permission Requirement](./requirement/permission-requirement.md)
* [Condition Requirement](requirement/condition-requirement.md)