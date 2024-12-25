---
icon: git-commit
order: 3
---
# v2.3

![](../../static/img/changelog/2.3.png)

This update features three major additions to Quillscript, among other things. It introduces **Named Parameters** in function calls, allows the use of **Nested Variable** patterns replacement, and provides many new features to the **Sprit Box**.

**Release Date**: 2024-08-22
**Engine Version**: 5.4

---

## <span class="command">Commands</span>

- Add support for **named parameters** in function call commands
- Add <span class="command">$ Sleep</span> built-in command
- Add <span class="command">$ Wakeup</span> built-in command

---

## Variables

- Refactored the **Replace Variables** function to handle nested variables patterns
- Add a Boolean return value to the Script reference's remove function, and a log message

---

## Widgets

- Add a content menu entry to create custom **Sprite Box** blueprints
- Add support for **Paper Sprite** asset type in the built-in **Sprite Box**'s Show function
- Add support for **Paper Flipbook** asset type in the built-in **Sprite Box**'s Show function
- Add support for **File Media Source** asset type in the built-in **Sprite Box**'s Show function
- Add support for **Material** asset type in the built-in **Sprite Box**'s Show function
- Add the **Size** function to the built-in **Sprite Box**
- Add the **FlipH** function to the built-in **Sprite Box**
- Add the **FlipV** function to the built-in **Sprite Box**
- Add basic gamepad support for the built-in widgets
- Add the tag **#auto** to the build-in Dialog Box widget
- Add getter functions and state variables to the Dialog Box to control auto proceed settings

---

## Extras

- Add **Find Property By Name** utility function
- Add **Is Same Unique Net ID** utility function
- Add **List Files** utility function
- Add **List Subdirectories** utility function
- Add **Launch File** utility function
- Add **Has Key Value Tag** utility function

---

## Fixes

- Fix a missing header preventing the plugin source code from compiling on Linux (clang)
- Fix a broken reference warning when packaging the game
- Fix an outdated code preventing the built-in Dialog Box's tags from working
- Fix an issue where a script reference of the same name can't be added twice
- Fix a misleading error message when _Update at Runtime_ is enabled while playing a transient script

---
