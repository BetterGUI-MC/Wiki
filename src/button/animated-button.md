# Animated Button

## Format
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

## Description
* This is a dynamic button.
* This will iterate through all the `child` buttons on every `update` ticks
* You can set the `async` value to make the `update` task asynchronously
* You can set the `shift` value to determine the start frame of the button
  * If you set a positive value (call `n`), the `n`-th frame will be the start frame
  * If you set a negative value (call `n`), the `n`-th frame from the bottom will be the start frame 
* You can set the `reverse` value to flip the child frames, so the frames will go bottom-up

## Example
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