# Template Button

## Format
```yaml
button-name:
  type: template
  template: <name> # The name from template folder
  variable:
    <variable1>: <value1>
    <variable2>: <value2>
    ...
  <button-settings>
```

## Description
* This button reduces the time you make the same button for every slots by setting it in a single template button in the `template` folder
  * The `template` folder is basically a folder containing `yml` files defining common buttons to use in all menus
  * You can get the registered template buttons by using the command [`gettemplatebuttons`](../Command-%26-Permission.md)
* You can use the `variable` option and set the variables for the template button. That will help you to create many buttons with different attributes from one single template button.

## Example

### Using Template Button

* **Normal Case**
```yaml
# Not using template
button1:
  id: stone
  name: "&cThis is button"
  lore:
  - "This is a line"
  - "This is a 2 line"
  - "This is a 3 line"
  - "This is a 4 line"
  command: "tell: &cYou clicked"

button2:
  id: stone
  name: "&cThis is button"
  lore:
  - "This is a line"
  - "This is a 2 line"
  - "This is a 3 line"
  - "This is a 4 line"
  command: "tell: &cYou clicked this again"
```

* **Using Template Button**
```yaml
# Using template
button1:
  type: template
  template: test # The name from template folder
  command: "tell: &cYou clicked"
button2:
  type: template
  template: test # The name from template folder
  command: "tell: &cYou clicked this again"

# Template File
test:
  id: stone
  name: "&cThis is button"
  lore:
  - "This is a line"
  - "This is a 2 line"
  - "This is a 3 line"
  - "This is a 4 line"
```

### Use `variable` option
```yaml
# This will create 4 buttons with different XP amount. These buttons give XP to the player
test-xp-100:
  type: template
  template: test-xp
  variable:
    xp: 100

test-xp-200:
  type: template
  slot: 12
  template: test-xp
  variable:
    xp: 200

test-xp-300:
  type: template
  template: test-xp
  variable:
    xp: 300

test-xp-400:
  type: template
  template: test-xp
  variable:
    xp: 400

# Template File
test-xp:
  id: paper
  name: "&eGive &f{xp} XP"
  lore:
  - ""
  - "&fThis is a test template button"
  command: "console: xp {xp} {player}"

# Notice that the template button has {xp} in it. It will be replaced with the value from the variables of the button using this template button
```
