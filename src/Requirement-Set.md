# Requirement Set

## Description
* A requirement set is a set of requirements that the player are required to pass.
* It consists of:
  * The [Requirements](./Requirement.md)
  * The [`success-command`](./Action.md) when the player passes all requirements
  * The [`fail-command`](./Action.md) when the player doesn't pass any of the requirements (rarely used)

## Example
```yaml
check-condition:
  slot: 1
  type: predicate
  CLICK-REQUIREMENT: # Click Requirement
    default: # Click type
      permission: # Requirement set name
        permission: # The permission requirement
        - bettergui.test
        - bettergui.test.1
        level: 10 # The level requirement
        fail-command: 'tell: &cYou don''t meet the requirements!'
        success-command: 'tell: &a[v] You passed the requirements!'
  button:
    NAME: '&8Requirement Test'
    LORE:
      - 'To use this item, you need to pass all requirements.'
      - 'Otherwise, a configurable error'
      - 'message will be displayed.'
    ID: iron bars
```