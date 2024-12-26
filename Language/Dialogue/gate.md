---
label: Gate
icon: cross-reference
order: 1
---
# Gate

Split a dialogue into two texts, one for true [condition](../condition/), and other for false

By default, when a dialogue condition fails, that dialogue line is ignored. A gate can select a different dialogue text if the condition fails.

- A Gate is defined by a **--- (_Triple Dashes_)**.

```q #
- Alice | ? {greet} == on
  Hey! --- Bye!
```

Also, with multiline dialogues:

```q #4
- Bob | ? {counter} > 3
  These lines show if
  counter is greater than 3
  ---
  These lines show
  otherwise
```

---
