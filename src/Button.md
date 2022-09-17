# Info
* A button is what is shown in the menu.
* When the player clicks a button, some actions are executed.
* A button can also be updated.
* There are many types of button. A developer can make his own button and register to the plugin.
* You can specify the type of button by setting the `type` option. By default, it will take the value of `default-button-type` from `config.yml`
# Type of Button
## Empty Button
* **The format**
```yaml
button-name:
  type: empty
```
* This is the simplest and useless button. This represents nothing.
## Dummy Button
* **The format**
```yaml
button-name:
  type: dummy # aliases: raw
  modifier1: <value1>
  modifier2: <value2>
  modifier3: <value3>
  ...
```
* This is a decorative button. You can only set the display item of the button through [Item Modifiers](https://github.com/BetterGUI-MC/BetterGUI/wiki/Item-Modifier)
* Example:
```yaml
dummy-button:
  type: dummy
  id: STONE
  name: "&eThis is a dummy button"
```
## Air Button
* **The format**
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
* This button represents the Air item, which the player can't see.
* You can only set 2 settings: [`action`](https://github.com/BetterGUI-MC/BetterGUI/wiki/Action) (command) and `close-on-click`
* Example:
```yaml
air-button:
  type: air
  command:
  - "tell: &aOh..."
  - "delay: 30"
  - "tell: &aUhhhh... Hello"
  close-on-click: true
```
## Null Button
* **The format**
```yaml
button-name:
  type: null
  # command:
  action:
  - <action>
  - <action>
  - <action>
  ...
  close-on-click: <true/false>
```
* This is similar to **Air Button**, but this button represents nothing.
* The difference is that, while **Air Button** overrides the display item and the actions of a slot, this button only overrides the actions of a slot
* Example:
```yaml
null-button:
  type: null
  command:
  - "tell: &aOh..."
  - "delay: 30"
  - "tell: &aUhhhh... Hello"
  close-on-click: true
```
## Simple Button
* **The format**
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
* This is a combination of **Dummy Button** and **Air Button**
* You can set the display item through [Item Modifiers](https://github.com/BetterGUI-MC/BetterGUI/wiki/Item-Modifier), and also set the 2 settings: [`action`](https://github.com/BetterGUI-MC/BetterGUI/wiki/Action) (command) and `close-on-click`
* Example:
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
## Animated Button
* **The format**
```yaml
button-name:
  type: animated # aliases: animate, anim
  update: <ticks>
  async: <true/false>
  shift: <number>
  reverse: <true/false>
  child:
    button1:
      <button-settings>
    button2:
      <button-settings>
    button3:
      <button-settings>
    ...
```
* This is a dynamic button.
* This will iterate through all the `child` buttons on every `update` ticks
* You can set the `async` value to make the `update` task asynchronously
* You can set the `shift` value to determine the start frame of the button
  * If you set a positive value (call `n`), the `n`-th frame will be the start frame
  * If you set a negative value (call `n`), the `n`-th frame from the bottom will be the start frame 
* You can set the `reverse` value to flip the child frames, so the frames will go bottom-up
* Example:
```yaml
animated-icon:
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
## Predicate Button
* **The format**
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
* This button will show the `button` if only the player meets the `view-requirement`, Otherwise the `fallback` button will be shown.
* You can set the `click-requirement` value if you want the plugin to check requirements when the player clicks the button.
* You can set the `check-only-on-creation` value to make the button only check `view-requirement` when the player opens the menu.
* Example:
  * https://github.com/BetterGUI-MC/BetterGUI/blob/42cf770e3e8bcb2dd6ca8e8b7264cca2c8bffb0d/src/main/resources/menu/example.yml#L143-L160
  * https://github.com/BetterGUI-MC/BetterGUI/blob/42cf770e3e8bcb2dd6ca8e8b7264cca2c8bffb0d/src/main/resources/menu/example.yml#L296-L307
## List Button
* **The format**
```yaml
button-name:
  type: list
  keep-current-index: <true/false>
  child:
    button1:
      <button-settings>
    button2:
      <button-settings>
    button3:
      <button-settings>
    ...
```
* This button will look through all the `child` buttons (top-down) and display a button if it can be shown
* You can set the `keep-current-index` value to make this button only check when the player opens the menu
* Example:
```yaml
list-icon:
  type: list
  keep-current-index: false
  child:
    world:
      type: predicate
      button:
        id: grass
        name: "&aYou are in {world}"
      view-requirement:
        condition:
          # STREQ: Compare 2 strings if they are the same
          condition: STREQ("{world}", "world")
    nether:
      type: predicate
      button:
        id: netherrack
        name: "&cYou are in {world}"
      view-requirement:
        condition:
          condition: STREQ("{world}", "world_nether")
    unknown:
      id: bedrock
      name: "&cYou are in {world}"
      lore:
        - "&cUnknown world"
```
## Template Button
* **The format**
```yaml
button-name:
  type: template
  template: <name> # The name from template-buttons.yml
  variable:
    <variable1>: <value1>
    <variable2>: <value2>
    ...
  <button-settings>
```
* This button reduces the time you make the same button for every slots by setting it in a single template button in the `template` folder
  * The `template` folder is basically a folder containing `yml` files defining common buttons to use in all menus
  * You can get the registered template buttons by using the command [`gettemplatebuttons`](https://github.com/BetterGUI-MC/BetterGUI/wiki/Command-&-Permission)
* For example, You can reduce the time you set these buttons with this button
```yaml
# Not using template-buttons.yml
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
```yaml
# Using template-buttons.yml
button1:
  type: template
  template: test # The name from template-buttons.yml
  command: "tell: &cYou clicked"
button2:
  type: template
  template: test # The name from template-buttons.yml
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
* You can use the `variable` option and set the variables for the template button. That will help you to create many buttons with different attributes from one single template button.
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
* Example:
  * Menu: https://github.com/BetterGUI-MC/BetterGUI/blob/50adf60cb54992d7b5fd97bb0ec2515d3526adc4/src/main/resources/menu/example.yml#L392-L439
  * Templates: https://github.com/BetterGUI-MC/BetterGUI/blob/master/src/main/resources/template/example-template.yml