---
label: Label
icon: "../../static/img/icons/label.svg"
order: 8
---
# Label

Labels are markers in specific points of your script flow. They are used as [routing points](../router/) to navigate from one point of the script to another, creating story branches and story flow control.

- A Label statement starts with an **@ (_At Sign)_**, immediately followed by a whitespace.
- The label name must be a **static name** with no variables or text replacements that can alter it during runtime.

```q #1,9
@ FirstLabel

- .
  This dialogue belongs to 'FirstLabel'.
- .
  This one also belongs to 'FirstLabel'.


@ SecondLabel

- .
  This dialogue belongs to 'SecondLabel'.
```

As written in the example above, all statements below the declaration of a label belong to that label section until another label is declared.

---

## <span class="label">Label as Instruction</span>
Any statement can be labeled by adding a label as instruction to it. Router statements can use these labels as any other label statement.

```q
- Alice | @MyDialogueLabel
  Hello!

* Hello | @MyOptionLabel

-> Target | @MyRouterLabel

$ x = 10 | @MyCommandLabel

? if: {x} == 10 | @MyConditionLabel

```

It's important to notice that statements can be jumped if they belong to a label statement with a false condition or when they are within a [condition statement](../condition/) that is also false. When a router statement points to a label instruction, the flow goes to that point, ignoring any parenting condition and evaluating only the target statement condition, if any.

---

## <span class="label">Display Name</span>
When naming labels, it's common to emerge project patterns that are often non-friendly, containing dots, slashes, prefixes, postfixes, and other marks.

If your project shows labels' names to users for some reason, like in a story tracker, these names are not ideal to be displayed to other developers or players.

You can type a free text line below your label declaration to add a user-friendly name.

```q
@ LabelStaticName
  Label User Friendly {name}
```

Differently from the label declaration itself, which must be a static name, a display name can use variables, replacements, rich text tags, and be formatted or modified by custom code.

---
