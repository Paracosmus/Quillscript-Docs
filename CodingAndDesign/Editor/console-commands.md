---
label: Console Commands
icon: terminal
---
# Console Commands

==- qsc.**Next**
Go to next story node

==- qsc.**Rollback**
Go to previous story node

==- qsc.**End**
Terminate script play

==- qsc.**Stop**
Block script from proceeding to other statements

==- qsc.**Restore**
Unblock script to proceed to other statements

==- qsc.**Play**
Go to given story node by index.

```rust Parameters
Index: positive integer. (0 if empty)
```

```sh
qsc.Play 72
```

==- qsc.**PlayByLabel**
Play given story node by label.

```rust Parameters
LabelName: string
```

```sh
qsc.PlayByLabel MyLabelName
```

==- qsc.**Car**
Set the value of a variable.

```rust Parameters
Name: string
LabelName: string
```

```sh
qsc.Var counter 10
```

==- qsc.**Del**
Delete a variable.

```rust Parameters
Variable: string
```

```sh
qsc.Del counter
```

==- qsc.**Eval**
Evaluate a Quillscript expression.

```rust Parameters
Expression: string
```

```sh
qsc.Eval ( 10 + 2 ) * 5 / 2
```

==- qsc.**Bypass**
Ignore all conditions set by script.

==- qsc.**NotBypass**
Stop ignoring conditions set by script.

==- qsc.**Debug**
Toggle Quillscript's debugger widget.

===

---
