---
icon: git-commit
order: 4
---
# v2.4

![](../../static/img/changelog/2.4.avif)

This update includes three major new features to add to Quillscript's pool of tools. It introduces the new [Dynamic Options](../../language/option/dynamic-options.md), [Smart Typewriter](../../coding-and-design/smart-text/smart-typewriter.md), and [Tooltip Text](../../coding-and-design/smart-text/rich-text.md#tooltip-decorator).

**Dynamic Options** are used to generate an options set during runtime. The **Smart Typewriter** is our new reusable object to display typewrite effect, text pauses and other functions. And **Tooltip Text** is an new text decorator used to display a tooltip text or widget when a substring is hovered inside a Rich Text Block.

**Release Date**: 2025-01-07
**Engine Version**: 5.5

---

## <span class="option">Options</span>

- Feature [Dynamic Options](../../language/option/dynamic-options.md)
    - **List Options**: Automatically add options to the options set using arrays and sets
    - **Inject Options**
        - **From Function Call**: Inject options into the options set using a Command Statement
        - **From Code**: Inject options into the options set using custom code

---

## <span class="command">Commands</span>

- Add the <span class="command">&HUD</span> shortcut to access the HUD object from script
- Add the <span class="command">&World</span> shortcut to access the World object from script
- Add the <span class="command">&Subsystem</span> shortcut to access the Quillscript Subsystem from script

---

## <span class="directive">Directives</span>

- The <span class="directive">~ checkpoint</span> Directive will evaluate its condition every frame if no interval is given.

---

## Script

- Add the **Set Script Play Counter** utility function
- Add the **Reset Script Play Counter** utility function
- <span class="blueprint">(Blueprint)</span> Blueprints can read and write Statement structs

---

## Widgets

- Add the [Smart Typewriter](../../coding-and-design/smart-text/smart-typewriter.md) object class
    - Reusable function
    - Timer delays
    - Substring delays
    - Typing sound
    - Sync duration with voice audio
- Update the built-in Dialog Box to use the new **Smart Typewriter** object and its new features
- Add the **Smart Text Block Decorator**, **Smart Text Decorator** and **Tooltip Text Style** classes to allow the use of tooltips and widget inside _Rich Text Blocks_.
    - [Show a tooltip text when a substring is hovered](../../coding-and-design/smart-text/rich-text.md#tooltip-text-style)
    - [Show a tooltip widget when a substring is hovered](../../coding-and-design/smart-text/rich-text.md#smart-text-block-decorator)

---

## Editor

- `qsc.BypassConditions` renamed to `qsc.Bypass`
- `qsc.NotBypassConditions` renamed to `qsc.NotBypass`

---

## Extras

- Add the **Play Typewriter Effect** utility function
- Add the **Property Exists** utility function
- Add the **Set Property by Name** utility function
- Add the **Get Property by Name** utility function
- Add the **Remove Rich Text Tags** utility function
- Add the **Get Variables in String** utility function
- Add the **Get Nested Widgets** utility function
- Add the **Get Nested Widgets of Class** utility function
- Add the **Remove Visible Widgets** utility function
- Add the **Remove Hidden Widgets** utility function
- Add the **Length** utility function
- <span class="cpp">(C++)</span> Add the **Find Property by Name** utility function
- <span class="cpp">(C++)</span> Add the **Insert Property by Name** utility function
- <span class="cpp">(C++)</span> Add the **STR()** macro to convert multiple types to _FString_
- <span class="cpp">(C++)</span> Add the **TXT()** macro to convert multiple types to _FText_
- <span class="cpp">(C++)</span> Add support to the print macros **PRINT()**, **SUCCESS()**, **WARNING()** and **ERROR()** for various types of data without the need for casting and conversions

---

## Fixes

- Fix an issue where the **Roll** function returns 0 when called from script while omitting the 'quantity' parameter
- Update deprecated code to UE 5.5 version
- Minor performance and stability improvements
- Minor code documentation improvements

---

## Possible Breaking Changes

!!!warning
The deprecated utility functions ~~Property to String~~ and ~~String to Property~~ were removed.

Use **Get Property by Name** and **Set Property by Name** instead
!!!

!!!warning
<span class="cpp">(C++)</span> The **Smart Text Block** class was moved from the _Widgets_ folder to the _Text_ folder.

It may be necessary to update the related `#include` paths
!!!

---
