---
label: Command
icon: "../../static/img/icons/command.svg"
order: 6
---
# Command

It's often required to execute programming code during your script play. Command statements can perform two tasks: Handle Quillscript Variables and Call Functions.

Quillscript is completely compatible with <a href="https://docs.unrealengine.com/latest/unreal-engine-programming-and-scripting/" target="_blank">Unreal Engine programming</a>, being it Blueprint Visual Scripting or C++, you can call almost any function from your script at any point.

- A Command statement starts with a **$ (_Dollar Sign_)**, immediately followed by a space.

```q #
// Quillscript variable handling
$ flag = on

// Function call
$ Play 1

```

[!ref](./quillscript-variables.md)

[!ref](./function-call.md)

---

## <span class="command">Command as Instruction</span>
A Command can also be concatenated to Dialogue, Option, and other Command statements as an instruction.

```q #
// In Dialogue.
- Bob | $ MyFunction
  Hello

// In Options.
* Hey   | greet = on | MyFunction
* Leave

// In other Command.
$ Restore | Play 5 | $ a = 10
```

!!!
Notice that the command marker **$ (_Dollar Sign_)** is not required in Command instructions and is implied.
!!!

You can concatenate as many Command instructions as required. They execute in the order they are written.

The Command instruction has a different behavior for each statement type.

<span class="dialogue">Dialogue</span>
:   Execute before the dialogue plays

<span class="option">Option</span>
:   Execute when the option is selected

<span class="command">Command</span>
:   Execute after the main command

---
