# Play Sound

## Format
* `sound: <sound>, [volume], [pitch]`
* `sound: <sound> [volume] [pitch]`
* `raw-sound: <sound>, [volume], [pitch]`
* `raw-sound: <sound> [volume] [pitch]`

## Description
* This action will send the `<sound>` to the player
* You can specify the `[volume]` and the `[pitch]` of the `<sound>`. Those are optional

## Example
* `sound: BLOCK_NOTE_BLOCK_PLING`
* `sound: BLOCK_NOTE_BLOCK_PLING 1 2`

## Note
* `<sound>` supports Minecraft's sound name, so it also supports custom sounds from Resource Pack. If the `<sound>` can not be found, the action is simply ignored
