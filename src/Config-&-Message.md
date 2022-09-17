### config.yml
```yaml
# The default type when loading menus from the "menu" folder
default-menu-type: simple

# The default type when loading buttons from the "menu" folder
default-button-type: simple

# Enable methics
metrics: true

# Use BetterGUI's Click Type with support for number keys
use-modern-click-type: false

# Whether the plugin replaces all similar variables on every check
replace-all-variables-each-check: true

# Force the inventory to be updated every refresh time
forced-update-inventory: false

# Use the legacy button that supports the old settings
use-legacy-button: true

# Command Override
alternative-command-manager:
  # Enable the override
  enable: false
  # Ignore case-sensitive when checking commands
  case-insensitive: true
  # Should we ignore the commands in ignored-commands
  # If set to false, the plugin will do the opposite (override the commands in ignored-commands)
  should-ignore: true
  # The list of ignored commands
  ignored-commands:
  - warp test
```
***
### messages.yml
```yaml
prefix: '&f[&bBetterGUI&f] '
prefix: '&f[&bBetterGUI&f] '
no-permission: '&cYou don''t have permission to do this'
player-only: '&cYou should be a player to do this'
success: '&aSuccess'
menu-required: '&cYou should specify a menu'
menu-not-found: '&cThat menu does not exist'
cooldown-message: '&cWait for {cooldown_second} secs ({cooldown}) before clicking again'
have-met-requirement-placeholder: 'Yes'
invalid-item: '&cUnable to get required item. Inform the staff'
invalid-number: '&cError converting! {input} is not a valid number'
invalid-amount: '&cInvalid amount of {input}! Will be set to 1 by default'
invalid-condition: '&cInvalid condition! Please inform the staff'
player-not-found: '&cThe player is not found. Maybe he is offline or didn''t join your server'
```