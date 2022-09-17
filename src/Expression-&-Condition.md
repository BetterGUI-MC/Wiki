# Info
* You may notice in some of the previous sections that I gave some weird values in some settings of the example menus like `STREQ("{world}", "world")` and `{level} > 5`
* Those are called Expression. That's the way we make complicated things in the menu (set the amount based on the level of the player, let the player click when the current world is the overworld, etc)
* We will talk about Expressions in the next sections
# Basic
* The basic is the use of math operators in the expressions (`+`, `-`, `*`, `/`, etc)
* Examples:
```yaml
amount: "5 + 7" # The amount will be 11
```
```yaml
amount: "{level} % 64 + 1" # The amount will be from 1 to 64, based on the level 
```
* Along with math operators, you can also use Boolean operators (`>`, `<`, `=`, `>=`, `<=`, etc) to compare values.
* Example:
```yaml
condition: "{level} > 5" # This will check if the player's level is higher than 5
```
* [Supported Operators](https://github.com/uklimaschewski/EvalEx#supported-operators)
# Function
* Functions are the process of "input to output", take the input and returns the corresponding output.
* [Functions](https://github.com/uklimaschewski/EvalEx)
* Example:
```yaml
amount: "FLOOR(SQRT(18))" # The amount will be the floor value of the square root of 18, which is 4
```
# String Functions
* BetterGUI also accepts comparing strings with String Functions
* It includes:
  * `STRCT("this", "is")` check if `is` is in `this` (`this` contains `is`)
  * `STREDW("String", "ing")` check if `String` ends with `ing`
  * `STREQ("str1", "str1")` check if `str1` equals `str1`
  * `STREQIC("str1", "str1")` check if `str1` equals `str1` (case-insensitive)
  * `STRLEN("Hello World")` get the length of `Hello World`
  * `STRMP("String", "String-?")` check if `String` matches the RegExr pattern `String-?`
  * `STRSTW("String", "Str")` check if `String` starts with `Str`