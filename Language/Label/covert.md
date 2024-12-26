---
label: Covert Label
icon: code
order: 2
---
# Covert

A covert label has the same behavior as a standard label, except that a covert label won't play unless explicitly called by a [Router](../router/). This means if the script flow ever reaches a covert label, it jumps to the following standard label.

A Covert Label starts with **<@> (_Less Than, At Sign, and Greater Than_)**, immediately followed by a whitespace.

```q #9,15
- Professor
  We do not have much time.

* Where are we?     | -> Where
* Can we eat first? | -> Eat
* Ok


<@> Where

  - Professor
    Downtown.


<@> Eat

  - Professor
    Of course not.


@ Continue

  - Professor
    Now, let's go.
```

In the example above, the **@Where** and **@Eat** labels only play if selected, and the story proceeds to **@Continue** jumping any covert labels on its flow.

---

## <span class="label">Covert Label as Instruction</span>
If a covert label is used as an instruction in other types of statements, that statement is also jumped unless it is called directly by a router.

```q
- Alice | <@>MyDialogueLabel
  Hello!

-> Target | <@>MyRouterLabel

$ x = 10 | <@>MyCommandLabel

? if {x} == 10 | <@>MyConditionLabel

```

---
