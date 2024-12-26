---
label: Quillscript Variables
icon: number
order: 3
---
# Quillscript Variables

A variable is **a** named location in memory that holds **a** value.

To declare **a** Quillscript variable, type the desired name, and use the **= (_Assignment Operator_)** to assign **a** value.

```q
$ my_variable = 10

```

Once assigned, you can use this data everywhere in your script and even in your Blueprint/C++ code.

```q #
$ name = Bob

- {name}
  Hello!
- {name}
  My name is {name}.
```

---

## Variable Type
Quillscript is an inferred type language, meaning that the variable type is automatically deduced. There are three variable types: **Switch**, **Number**, and **Text**. The variable type is used to determine the behavior of this variable for each operator, **a** Number type variable can be used for math operations, for example.

### Switch
Represents an **on**/**off** state, also known as **Boolean**.

```q
$ flag = on
$ state = off

```

### Number
For numeric values. **Integers** and **floating points**.

```q
$ number = 10
$ negative = -79
$ fraction = 4.88

```

### Text
For **string** values.

```q
$ word = hello
$ text = Hi! My name is Ed.

```

---

## Variable Access
The variable mark describes how Quillscript interpreter handles its lifecycle and other automatized tasks.

### Global
By default, any Quillscript variable is global. Once created, **a** global variable can be used in any other script, allowing script intercommunication.

!!!
Use global variables when persistence or intercommunication is necessary, and use temporary variables otherwise, since persistent variables take memory space, increase save file size, and increase the duration of certain tasks, like variable replacement in texts and expressions.
!!!

### Temporary Variables
A Temporary Variable is **a** Quillscript variable that only exists during that script play. Temporary variables are automatically deleted when the script ends.

These variables are the preferred method for declaring variables when they don't need to exist after **a** script play. The use of these variables saves computing resources, since Quillscript has **a** smaller list of variables to search and apply tasks.

To declare **a** Temporary Variable, you name it starting with **: (_colons_)**.

```q
$ :greetings = on
$ :name = Doug

```

### Outer Variables
Quillscript creates these variables to capture the return value of called functions. They have the same lifecycle of temporary variables and are deleted when the script ends. Check [Function Call](./function-call.md) section for more details.

### Template Variables
These variables are created by Quillscript to be used as arguments by **a** template call. They are deleted when **a** label statement is reached. Check Template section for more details.

---

## Assigning Variables
Besides assigning static hard-coded values, variables also accept math expressions and other value concatenation methods.

### Expressions
You can assign **a** complete math expression to **a** single variable, from **a** simple addition to **a** complex equation.

```q
$ x = 10 + 5
$ y = ((2 + 2) * 4) ^ 2

```

It's possible to use other variable values in expressions. Notice the use of **{} (_brackets_)** to use **a** variable value instead of the literal string _"value"_.

```q
$ value = 5
$ result = {value} / 2

```

You can self-reference the assigned variable in an expression using **a** **{&}**.

```q
$ value = 10
$ value = {&} + 5
// value equals 15
```

Or use **a** reduced assignment operation.

```q
$ value += 10
$ value -= 10 + 2
$ value *= 5
$ value /= 5 - 6
$ value %= 2 * 2
$ value ^= 2

```

#### Valid Operators

| {.compact}
--- | --- | ---
<span class="command">or</span>   | Logical OR | Check if **a** or **b** is <spam class="keyword">on</span>
<span class="command">and</span>  | Logical AND | Check if **a** and **b** are <spam class="keyword">on</span>
<span class="command">==</span>   | Equal | Check if **a** equals **b** (case insensitive)
<span class="command">\===</span> | Strict Equal | Check if **a** equals **b** (case sensitive)
<span class="command">!=</span>   | NOT Equal | Check if **a** not equals **b** (case insensitive)
<span class="command">!==</span>  | Strict NOT Equal | Check if **a** not equals **b** (case sensitive)
<span class="command"><</span>    | Less | Check if **a** less than **b**
<span class="command"><=</span>   | Less Equal | Check if **a** less or equal **b**
<span class="command">\></span>   | Greater | Check if **a** greater than **b**
<span class="command">\>=</span>  | Greater Equal | Check if **a** greater or equal **b**
<span class="command">\+</span>   | Addition | Sum **a** plus **b**
<span class="command">\-</span>   | Subtraction | Subtract **b** from a
<span class="command">\*</span>   | Multiplication | Multiply **a** for **b**
<span class="command">/</span>    | Division | Divide **a** by **b**
<span class="command">%</span>    | Remainder | Find the remainder of **a** divided by **b**
<span class="command">^</span>    | Power | Power **a** by **b**

!!!warning
On **Less**, **Less Equal**, **Greater**, **Greater Equal**, **Addition**, **Subtraction**, **Multiplication**, **Division**, **Remainder**,and **Power** operations, it's required that the operands are numeric values. If a non-numeric value is passed, it is converted as follows:

- on to 1
- off to 0
- A Text values is converted to numeric if possible, and to 0, otherwise.
!!!

### Constructor
The operator **constructor (:=)** is used to assign a value to a variable only if that variable does not exist. This is useful for setup a script on its first play.

Complement the **assignment (=)** operator with the **new (:)** operator:

```q
$ x := 1 + 1

```

This is the same as `$ x = 1 + 1`, but is executed only if there isn't already a variable called **x**.

### Text Concatenation
The use of brackets allows the formation of texts by concatenation.

```q
$ name = Dennis
$ surname = Ritchie
$ full_name = {name} {surname}

$ text = Hello Mr. {surname}.

```

### Nested Variables Replacement
The use of brackets can also be done nesting **a** variable inside other variable brackets.

```q #20
$ place_LeftFight = Arena
$ place_LeftTrade = Store

$ place_RightFight = Stadium
$ place_RightTrade = Market

- .
  Do you turn left or right?

* I go left  | direction = Left
* I go right | direction = Right

- .
  And what do you want?

* Fight | place = Fight
* Trade | place = Trade

- .
  You arrive at the {place_{direction}{place}}.
```

It is possible to use more elaborated replacement pattern if necessary

```q
{ {varName}}, { {var1}{var2}}, {text_{var}}, { { {var1}_text}_{var2}{var3}}, etc.
```

---

## Constants
Constants work just like variables, they are assigned and handled the same way, but once created, they can't have their value changed.

Constants are declared on all uppercase.

```q
$ CONST = 10
$ NAME = Alice
$ PI = 3.14

```

---

## Deleting Variables
You should always remove variables that aren’t required to be permanently stored, as the more variables there are, the more time it takes to execute some tasks.

To delete a variable, call the built-in function [Delete](./built-in-functions.md) and pass the variable's name.

```q
$ Delete name

```

!!!
Temporary variables are automatically deleted when the script ends, but you can delete them manually if needed.
!!!

---

## Localizing Variables' Text
Although being stored as an Unreal Engin's Text type, Quillscript's Text variables are marked as cultural invariants by default. If the value of a variable must be localized, set its value inside **`` (_backticks_)**

```q
$ response = `This text is localizable.`

```

---

## Using Variables in Code
Quillscript variables are stored as an <a href="https://dev.epicgames.com/documentation/unreal-engine/map-containers-in-unreal-engine" target="_blank">Unreal Engine Map</a> of <a href="https://dev.epicgames.com/documentation/unreal-engine/fname-in-unreal-engine" target="_blank">Name</a> to <a href="https://dev.epicgames.com/documentation/unreal-engine/ftext-in-unreal-engine" target="_blank">Text</a>. This map is declared in Quillscript Subsystem and is accessible in Blueprints and C++. Check <a href="../../coding-and-design/libraries/quill.md" target="_blank">Quillscript Static Library</a> for detailed usage.

---

## Variable Modifier
Check [Register Variable Modifier](../../coding-and-design/libraries/quill.md#register-variable-modifier) and [Unregister Variable Modifier](../../coding-and-design/libraries/quill.md#unregister-variable-modifier).

!!!ghost
:construction: Under construction :construction:
!!!

---

## Hard Coding Default Variables

!!!ghost
:construction: Under construction :construction:
!!!

---
