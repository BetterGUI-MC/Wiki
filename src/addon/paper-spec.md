# PaperSpec
> [Code](https://github.com/BetterGUI-MC/PaperSpec/) | [Download](https://ci.codemc.io/job/BetterGUI-MC/view/Addon/job/PaperSpec/)

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