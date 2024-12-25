---
label: Condition
icon: "../../static/img/icons/condition.svg"
order: 5
---
# Condition

Another important aspect of creating story branches is Conditions. When writing a story, you often need a story section to be played only in specific states.

Conditions allow you to check if a specific statement or section should be played or ignored by running an expression evaluation first. If the evaluation returns on _(true)_, the condition is successful, and the line is played. If the condition fails, the line is ignored.

- A condition statement can optionally start with a **? (Question Mark)**
- A condition statement is named after its functionality
    - **If:** Check an initial condition
    - **elseif:** Check as many secondary conditions as needed
    - **else:** This section plays if all if and elseif conditions fail
- A conditions statement sequence must always end with an **endif** marker

```q #6,17
$ quest_completed = off

- Father Morgan
  Back so soon?

? if: {quest_completed} == on

  - Matt
    The job is done.

  - Father Morgan
    I'm pleased to hear this.
    Here, take this as a token of gratitude.

  $ AddItem PriestRobes

? endif

- Matt
  See you later, father.
```

In the example above, the script section from line 6 to line 17 is played only if the condition on line 6 is evaluated as true.

Using **elseif** and **else** conditions are completely optional. You can use as many **elseif** as required.

```q #7,17,27,40
$ price = 100
$ barter = 5

- You
  Can you give me a discount?

if: {barter} > 8

  - Shopkeeper
    Ok, you can keep it for half price.

  - You
    That is awesome!

  $ gold = {&} - ( {price} * 0.5 )

elseif: {barter} >= 4 AND {barter} <= 8

  - Shopkeeper
    Best I can do is 10%.

  - You
    Deal!

  $ gold = {&} - ( {price} * 0.9 )

else:

  - Shopkeeper
    You're kidding me! Right?

  - You
    Hmmm! No?!

  - Shopkeeper
    Get out of my shop!

  $ reputation = {&} - 2

endif

- .
  Time to leave.
```

You can nest **if** conditions inside each other, just remember to close each individual _"if's collection of statements"_ with an **endif** statement, as shown above.

---

## Expression
A condition is always an [expression](../Command/quillscript-variables.md#expressions), the same method used to assign value to a variable. Therefore, conditions can use the same operators and syntax used by command expressions and be as complex as required.

```q #
- Bob | ? {x} + {y} > (10 ^ ({x} / 2)) OR ({x} == 5 AND {y} / 2 > 3)
  Hello!

- Alice | ? {name} != Bob OR {switch} == on
  Hello!
```

---

## Condition as Instruction
You can use a condition instruction within any other statement to check if that single statement can be played or should be ignored.

- A condition instruction starts with a ? (Question Mark) followed by an expression.

```q
$ End | ? {var} == off
```

A condition instruction is successful when its expression is evaluated as **on** and fails in any other case.

```q
$ charisma = 10

- Shopkeeper | ? {charisma} >= 5
  All right, it's a deal, you can keep the horse.

- Shopkeeper | ? {charisma} < 5
  Get out of my shop.
```

In the first dialogue, the interpreter checks if a previously created Quillscript variable has a value bigger or equal to 5. The second dialogue covers the remaining option, that is, if _charisma_ is smaller than 5.

You can add as many conditions as needed to a single statement.

### In Dialogue, Router, and Command
If any condition instruction fails, the statement is ignored, and the script flow proceeds to the following statement.

### In Option
Conditions are pre-evaluated and passed to the Play event of the Selection Box widget as a Boolean parameter called Valid. This parameter does nothing by itself; it’s delegated to the Selection Box widget to decide what to do with this information. In most cases, the widget hides, gray out, or lock invalid options.

```q
* Kiss her | ? {charisma} > 4 | -> Kiss
* Bye!                        | -> Leave

```

### In Label
The label and its content are ignored if any condition instruction fails, and the script flow proceeds to the following label statement.

```q
@ Leave | ? {charisma} > 4
  This section is ignored if charisma <= 4
```

---
