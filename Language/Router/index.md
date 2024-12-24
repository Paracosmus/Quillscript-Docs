---
label: Router
icon: "../../static/img/icons/router.svg"
order: 7
---
# Router

Routers are navigation controllers to move from one point of the story to a given label, by name. Its main functionality is control where the story should move to, based on player choices, variable values, and custom code.

- A Router statement starts with a **-> (_Dash and Greater Than_)**, immediately followed by a space.

```q #1
-> Finish

// This label is jumped.
@ Story

// The script flow moves to this label.
@ Finish

```

---

# Router as Instruction
A Router can also be concatenated to other statements and used as an instruction.

In **Dialogue**, **Label**, **Command**, and Other **Router** statements, a router instruction is executed only if the statement conditions fail.

```q
$ courage = 1

- Alice | ? {courage} >= 5 | -> Flee
  I will fight
```

```q
$ x = 1

@ Mylabel | ? {x} == 0 | -> MyOtherLabel

```

```q
$ move = off

-> Mylabel | ? {move} == on | -> MyOtherLabel

```

```q
$ coins = 25

$ End | ? {coins} >= 50 | -> Pay

```

In **Option statements**, a router instruction is executed when that option is selected.

```q
- .
  You're flanked.

* Be brave and stay            | -> Fight
* Be cautious and try to leave | -> Flee

```

---
