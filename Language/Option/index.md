---
label: Option
icon: "../../static/img/icons/option.svg"
order: 9
---
# Option

Another essential element for games with story branching is asking the player what they want to do or say in a specific situation. This is expressed in Quillscript as an Options collection.

An Option statement starts with an **\* (_asterisk_)**, immediately followed by a whitespace.

```q #
- Innkeeper
  Do you want to rent a room?

* Yes, please.
* No, thank-you.
```

!!!
You can sequence as many options as you want; just remember to design your [Selection Box](../../CodingAndDesign/Widgets/selection-box.md) widget accordingly.
!!!

---

## Multiline Text Option

Options' texts can also come in multiple lines, using a second asterisk, and adding the option text in the following line.

```q #4
- Innkeeper
  Do you want to rent a room?

* *
  Yes, please.
  With a big bed and view.

* No, thank-you.
```

---

## Navigation

As you can see, the above options do nothing after being chosen. You can use an option to move to a desired point of the story by concatenating a [Router as instruction](todo).

```q #4,5,8,13
- Jack
  Where should we go?

* New York city. | -> NewYork
* Los Angeles.   | -> LosAngeles
* Home.          | $ End

@ NewYork
- Jack
  New York! New York!
$ End

@ LosAngeles
- Jack
  All right let's go meet some celebrities.
$ End

```

---

## Execute Commands
Another common use is executing a [Command as instruction](todo) within an option, like handling a variable or calling a function.

```q #4-6
- Alice
  What is your name?

* Jack    | name = Jack
* Richard | name = Richard
* Tom     | name = Tom

- {name}
  My name is {name}
```

---
