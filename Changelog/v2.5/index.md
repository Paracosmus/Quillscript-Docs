---
icon: git-commit
order: 5
---
# v2.5

![](../../static/img/changelog/2.5.png)

**Release Date**: 2025-10-08
**Engine Version**: 5.6, 5.7

---

This release brings features, improvements, and fixes to enhance your experience with Quillscript. Notable additions include support for **interfaces in function calls**, **RPG dice expressions** in commands, and various utility functions. Additionally, several bugs have been addressed to improve stability and performance.

---

## <span class="command">Commands</span>

- Add support for **Interfaces** to the Function Call by class command
- Support for RPG dice regular expressions pattern in commands and conditions expressions
    - Ex.: `{1d6} + 2 + ( {2d20} / 3 )`
- Delay the execution of the <span class="command">$ Show</span> command to the next frame to avoid potential issues when showing widgets during the same frame they are draw and to allow the next statement to execute properly before the widget is shown

---

## Extras

- Add the **Regex Match** utility function
- Add the **Get World Type as String** utility function
- Add the **Asset Exists** utility function
- Add the **Load Asset by Path** utility function
- <span class="blueprint">(Blueprint)</span> Add the **Is Running** blueprint macro
- <span class="blueprint">(Blueprint)</span> Add the **Is World Type** blueprint macro
- <span class="cpp">(C++)</span> Add the **LOAD\<typename\>** utility macro to load assets by path
- <span class="cpp">(C++)</span> Add support for _Guid_, _Gameplay Tags_ e _Gameplay Tag Containers_, _Date Time_, _Timespan_, _Timecode_ to the **STR()** macros

---

## Fixes

- Fix an issue where the _Input Settings After_ are not applied properly on script ended, when the script is the final end of a <span class="command">$ Travel</span> sequence
- Fix an issue when trying to print an **UEnum** using the [Print](/coding-and-design/libraries/tools.md#print) set of functions
- Fix an issue where the previous voice asset duration was being used to all future dialogue typewriting speed.
- Fix an issue preventing the use of _slot positioning_ with the built-in **Sprite Box**
- Fix an issue causing the Interpreter widgets to be restored at the wrong layer after being hidden
- Fix an issue where the <span class="command">$ Timer</span> command triggers <span class="command">$ Next</span> even when asynchronous execution is enabled
- Improve the **UQuillscriptSubsystem::World()** function to make it safer
- Minor performance and stability improvements
- Minor code documentation improvements

---
