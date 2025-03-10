---
label: Dynamic Options
icon: key-asterisk
order: 1
---
# Dynamic Options

Dynamic options are used when you don't know the options at design time. They are generated at runtime based on some conditions or data. This is useful when we want to provide a list of options based on some user input or from a data model.

To create dynamic options, you can use add a second **\* (asterisk)**. This tells the interpreter that the option is dynamic and will be generated at runtime.

---

## <span class="option">From List</span>

The interpreter will automatically generate the options based on the array or set. Add an **\* (asterisk)** before the array/set variable name and the interpreter will generate a set of options based on that array entries.

```q #7
// Store all save game slot names into an array called '$ReturnValue'
$ ^Quillscript.Tools.GetAllSaveGameSlotNames

- .
  Select a save slot.

* * {*$ReturnValue} | $ $MyObject.LoadGame {*$ReturnValue}
* Don't load
```

You can use as many arrays or sets as you want. The interpreter will generate the options based on the index of each entry and stop on the size of the smallest array.

```q #10
// Fictional custom function to get all the players names into an array ($PlayersNames).
$ &GameMode.GetPlayersNames

// Fictional custom function to get all the players scores into a set ($PlayersScores).
$ &GameMode.GetPlayersScores

- .
  Select a player.

* * {*$PlayersNames} | $ $MyObject.CheckScore {*$PlayersScores}
* Continue
```

---

## <span class="option">From Command</span>

This method is used when you need more code control to generate the options. You can use a custom function to generate the options and insert them in the position.

The interpreter will execute the command responsible to generate the options and insert it in the position.

```q #4
- .
  Fast travel to:

* * | $ &MyObject.GenerateAvailableTravelOptions
* Continue
```

And your options function will inject the options into the **Inject Options** array from the _Quillscript Subsystem_.

[!embed](https://blueprintue.com/render/bvupk1ay/)

!!!
You can also use this method to direct inject options from code, without the need to call it from script.
!!!

---
