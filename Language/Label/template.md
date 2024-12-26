---
label: Template
icon: mention
order: 1
---
# Template

Templates are a specific type of [covert labels](./covert.md) that receive entry arguments. A variable is created for each argument and exists until a new label statement is played.

This can reduce repetitive lines and play specific sections of a story that need entry parameters.

- Since templates are also covert labels, they can be declared using either **@** or **<@>**
- After naming the label, enumerate a list of arguments between parentheses, and separate by commas
- Template argument variables start with **@**
- On the router statement, pass the values for each argument in the same order.

```q #
@ Id (name, surname, job)

  - {@name} {@surname}
    I'm the {@job}.


@ Start

  - Guard
    Identify yourselves.

  $ family = Wilson

  <-> Id (Oliver, {family}, tailor)
  <-> Id (Amelia, {family}, merchant)

  - Guard
    All right. You can come in.
```

---

## <span class="label">Template as Instruction</span>
A label instruction can also be a template. In this case, the statement only plays if directly called by a router, since it becomes a covert statement.

Template variables are created for this statement play and deleted on the following statement play.

```q
-> Intro (name, sentence)

- {@name} | @Intro (John, Tell him to move on.)
  {@sentence}
```

---
