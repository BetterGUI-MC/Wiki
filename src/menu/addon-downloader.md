# Addon Downloader

## Format
```yaml
menu-settings:
  menu-type: addon
  name: '&c&lAddon Downloader'
  rows: 3
  command:
    - addondownloader
    - addondl
  auto-refresh: 5

button:
  material:
    - LIGHT_BLUE_STAINED_GLASS_PANE
    - STAINED_GLASS_PANE:3
  name: "&f{name} &c- &4{status}"
  lore:
    - "&f{description}"
    - "&fAuthors: &e{author}"
    - "&fVersion: &e{version}"
    - ""
    - "&bLeft click &fto download"
    - "&bRight click &fto get the source code"
    - "&bMiddle click &fto see the wiki"
```

## Description
* This is a special menu that displays the available addons of BetterGUI.
* You can view the addons and read their wiki
* You can also download addons and they'll be installed automatically (Requires restarting the server after downloading to enable the addons)