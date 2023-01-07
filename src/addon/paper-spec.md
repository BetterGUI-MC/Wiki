# PaperSpec
> [Code](https://github.com/BetterGUI-MC/PaperSpec/) | [Download](https://ci.codemc.io/job/BetterGUI-MC/view/Addon/job/PaperSpec/)

## Description
This addon add functions that only works on [PaperMC](https://papermc.io/) and its forks. This addon requires Paper 1.18 or newer to work.

## Item Modifier

### Skull Modifier

#### Format
```yaml
paper-skull: <skull>
paper-head: <skull>
```

#### Description
* This modifier will set the `<skull>` of the item
* `<skull>` accepts a player name or an UUID (unique id)

#### Example
```yaml
skull:
  position-x: 1
  position-y: 1
  name: "&bSkull"
  id: player_head
  paper-skull: "HSGamer"
  #paper-skull: "7acc67dc-8b84-4f8d-b7ad-ec81e758f5a1"

per-player-skull:
  position-x: 2
  position-y: 1
  name: "&bPer Player Skulls"
  id: player_head
  paper-skull: "{player}"
```

### DisplayName & Lore

#### Format
```yaml
mini-name: <minimessage formatting text>
mini-lore:
- <minimessage formatting text>
- <minimessage formatting text>
- ...
```

#### Description
You can use [MiniMessage formatting](https://docs.adventure.kyori.net/minimessage/index.html) for the name and lore of your menu items. Just make sure you use the new format below instead of the original `name` and `lore` modifiers.

There are aliases for the modifiers. You can also use `name$` for the `mini-name`, and `lore$` for the `mini-lore`.

Note that the legacy color codes (`&c`, `&3`) does not work in the

#### Example
```yaml
minimessage:
  position-x: 1
  position-y: 1
  mini-name: "<rainbow>Rainbow Name"
  mini-lore:
    - "<b>Bold text"
    - "<aqua>Simple color!"
    - "<#00ff00>R G B color!"
    - "<gradient:green:blue>Gradient color!"
    - "<transition:#00ff00:#ff0000:0>Transition color!"
    - "<font:myfont:custom_font>Uses a custom font from a resource pack"
    - "<lang:block.minecraft.diamond_block> <- this is a translatable text"
```
