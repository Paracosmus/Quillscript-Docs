---
label: Repeater
icon: kebab-horizontal
order: 2
---
# Repeater

It's common to have a story section where the same character talks successively, causing repetition. You can use this shortcut to avoid repetitive Dialogue header lines. The Repeater is replaced by the last valid Dialogue header line.

- A Repeater is defined by a **... (_Triple Dots_)**.

```q #3,5
- Dumbledore
  It is our choices, Harry,
- ...
  that show what we truly are,
- ...
  far more than our abilities.
```

A repeater copies the **character name**, **conditions**, and **tags**.

```q #1
- Boss | ? {charisma} < 8 | #angry
  I do not like you.
- ...
  I do not like your attitude.
- ...
  And I do not like your face.
```

---
