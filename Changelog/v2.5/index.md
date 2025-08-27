---
icon: git-commit
order: 5
---
# v2.5

![](../../static/img/changelog/2.5.png)

!!!
This version is a **work in progress**. It is not yet available for public use.

When a new feature is completed, it will be added to the list. Please note that this is not a complete list of all changes and improvements yet.

New features and improvements are being added regularly, so stay tuned for the final release!
!!!

**Release Date**: 2025-MM-DD
**Engine Version**: 5.X

---

## <span class="command">Commands</span>

- Add support for **Interfaces** to the Function Call by class command
- Support for RPG dice regular expressions pattern in commands and conditions expressions
    - Ex.: `{1d6} + 2 + ( {2d20} / 3 )`

---

## Extras

- Add the **RegexMatch** utility function
- Add the **Get World Type as String** utility function
- Add the **Asset Exists** utility function
- Add the **Load Asset by Path** utility function
- <span class="blueprint">(Blueprint)</span> Add the **Is Running** blueprint macro
- <span class="blueprint">(Blueprint)</span> Add the **Is World Type** blueprint macro
- <span class="cpp">(C++)</span> Add the **LOAD\<typename\>** utility macro to load assets by path
- <span class="cpp">(C++)</span> Add support for _Guid_, _Gameplay Tags_ e _Gameplay Tag Containers_, _Date Time_, _Timespan_, _Timecodeto_ the **STR()** macros

---

## Fixes

- Fix an issue where the _Input Settings After_ are not applied properly on script ended, when the script is the final end of a <span class="command">$ Travel</span> sequence
- Fix an issue when trying to print an **UEnum** using the [Print](/coding-and-design/libraries/tools.md#print) set of functions
- Improve the **UQuillscriptSubsystem::World()** function to make it safer
- Minor performance and stability improvements
- Minor code documentation improvements

---
