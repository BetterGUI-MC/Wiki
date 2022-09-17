# Info
* Item Modifier is the property of an item. It describes what the final item should be.
* There are a lot of modifiers for items. A developer can also make his own modifier and register to the plugin.
# Modifiers
## Material
* **The format**
```yaml
material: <material>
id: <material>
mat: <material>
```
* This modifier will set the `<material>` of the item
* [List of Materials](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html)
* You can see a lot of examples of this modifier in the example menu
## Raw Material
* **The format**
```yaml
raw-material: <material>
raw-id: <material>
raw-mat: <material>
```
* This modifier will set the `<material>` of the item
* This uses your server version of `<material>`, so it supports custom materials (Probably from Forge/Bukkit server like Mohist)
## Name
* **The format**
```yaml
name: "<name>"
```
* This modifier will set the display `<name>` of the item
* You can see a lot of examples of this modifier in the example menu
## Lore
* **The format**
```yaml
lore: <lore>
```
```yaml
lore:
- <lore>
- <lore>
- <lore>
...
```
* This modifier will set the `<lore>` of the item
* You can see a lot of examples of this modifier in the example menu
## Amount
* **The format**
```yaml
amount: <amount>
```
* This modifier will set the `<amount>` of the item
* You can see a lot of examples of this modifier in the example menu
## Durability
* **The format**
```yaml
durability: <durability>
damage: <durability>
```
* This modifier will set the `<durability>` of the item
* An example for this can be found in the example menu: [Here](https://github.com/BetterGUI-MC/BetterGUI/blob/17209a29e6b9948fd15991916a25a42763a68c6a/src/main/resources/menu/example.yml#L53)
## Enchantment
* **The format**
```yaml
enchantment:
- <enchantment>, [level]
- <enchantment>, [level]
- <enchantment>, [level]
...
```
```yaml
enchant:
- <enchantment>, [level]
- <enchantment>, [level]
- <enchantment>, [level]
...
```
```yaml
enc:
- <enchantment>, [level]
- <enchantment>, [level]
- <enchantment>, [level]
...
```
* This modifier will add the `<enchantment>`s to the item
* [List of Enchantments](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/enchantments/Enchantment.html)
* You can set the `[level]` of the `<enchantment>`. It's optional.
* An example for this can be found in the example menu: [Here](https://github.com/BetterGUI-MC/BetterGUI/blob/17209a29e6b9948fd15991916a25a42763a68c6a/src/main/resources/menu/example.yml#L62-L63)
## Item Flag
* **The format**
```yaml
flag:
- <flag>
- <flag>
- <flag>
...
```
```yaml
item-flags:
- <flag>
- <flag>
- <flag>
...
```
```yaml
itemflag:
- <flag>
- <flag>
- <flag>
...
```
```yaml
itemflags:
- <flag>
- <flag>
- <flag>
...
```
```yaml
item-flag:
- <flag>
- <flag>
- <flag>
...
```
* This modifier will add the `<flag>` to the item
* [List of flags](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/ItemFlag.html)
* An example for this can be found in the example menu: [Here](https://github.com/BetterGUI-MC/BetterGUI/blob/17209a29e6b9948fd15991916a25a42763a68c6a/src/main/resources/menu/example.yml#L229-L230)
## Potion Effect
* **The format**
```yaml
potion:
- <potion> [duration] [amplifier]
- <potion> [duration] [amplifier]
- <potion> [duration] [amplifier]
...
```
```yaml
effect:
- <potion> [duration] [amplifier]
- <potion> [duration] [amplifier]
- <potion> [duration] [amplifier]
...
```
* This modifier will add the `<potion>` effect to the item
* [List of Potion Effects](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/potion/PotionEffectType.html)
* You can set the `[duration]` and `[amplifier]` of the `<potion>` effect. These are optional.
* An example for this can be found in the example menu: [Here](https://github.com/BetterGUI-MC/BetterGUI/blob/17209a29e6b9948fd15991916a25a42763a68c6a/src/main/resources/menu/example.yml#L384-L386)
## Skull
* **The format**
```yaml
skull: <skull>
head: <skull>
skull-owner: <skull-owner>
```
* This modifier will set the `<skull>` of the item
* `<skull>` accepts a player name, an UUID (unique id), an Base64 value, or a `texture.minecraft.net` URL
* An example for this can be found in the example menu: [Here](https://github.com/BetterGUI-MC/BetterGUI/blob/17209a29e6b9948fd15991916a25a42763a68c6a/src/main/resources/menu/example.yml#L367-L370)
## NBT
* **The format**
```yaml
nbt: <nbt>
nbt-data: <nbt>
```
* This modifier will apply the `<nbt>` to the item
* Example: 
```yaml
nbt: '{display: {color: 8910400}}'
```