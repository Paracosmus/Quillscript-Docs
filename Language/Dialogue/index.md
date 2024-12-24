---
label: Dialogue
icon: "../../static/img/icons/dialogue.svg"
order: 10
---
# Dialogue

An essential element of any text-based story is dialogue. Even in purely narrated games, the narrator has to say something or expose events and ideas to the player.

A Dialogue statement is composed of two or more lines.

- The first line starts with **- (_dash_)**, immediately followed by a whitespace. The dialog metadata represents information like the speaker’s name and conditions.
- The subsequent lines are the dialogue itself, the sentence being said.


```q #
- .
  One Ring to rule them all, One Ring to find them,
  One Ring to bring them all, and in the darkness bind them,
  In the Land of Mordor where the Shadows lie.
```

!!!
As a best practice, we use a . (dot) to express this is a narrator's text.
!!!

You can write character interactions putting together as many dialogues as necessary to create a conversation.

```q #
- Bob
  Hi, Alice! How are you?

- Alice
  Hi, Bob! I'm fine.
  Thank you!
```

---
