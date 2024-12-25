---
icon: git-commit
order: 1
---
# v2.1

![](../../static/img/changelog/2.1.jpg)

This is the first major update for Quillscript since it became the plugin's main branch. It adds new features like new built-in functions, the Inject directive, and some new delegates, among other things. It also fixes issues with commands and saving.

**Release Date**: 2023-08-02
**Engine Version**: 5.2

---

## <span class="command">Commands</span>

- Add built-in function <span class="command">$ Voice</span>
- Add built-in function <span class="command">$ Music</span>
- Add built-in function <span class="command">$ SFX</span>
- Add built-in function <span class="command">$ PlayAnimation</span>
- Add built-in function <span class="command">$ Timer</span>
- Add built-in function alias <span class="command">$ Bg</span>

---

## <span class="directive">Directives</span>

- Add the <span class="directive">~ inject</span> directive

---

## Subsystem

- The **On Script End** event now have a Script Id parameter

---

## Scripts

- Local Script Settings will keep its original value instead of updating to Project Defaults
- Add **On Variable Set** delegate
- Scripts linked by Id in directives or Travel will now be properly linked in the reference viewer

---

## Interpreter

- The <span class="command">$ Travel</span> built-in function accepts referencing scripts by id
- The <span class="command">$ Travel</span> built-in function won't apply 'Script Settings After' on script change

---

## Widgets

- It's now possible to override the Play method on child C++ classes

---

## Settings

- Add **Manage Background Box** setting
- Add the **Get Settings Asset by Path** helper function
- Default variables and references from Settings Assets are properly added on Script Asset set

---

## Extra

- Add **Remove Accentuation** function
- Add **Property to String** function
- Add **String to Property** function
- Minor improvements to performance and stability

---

## Fixes

- Fix an issue preventing commands to call functions by class
- Fix some minor issues with default widget's rich text and components
- Fix a missing include preventing compile on Mac OS
- Fix a crash during save
- Fix an issue causing a crash when the Script Target reference was mistakenly Garbage Collected

---
