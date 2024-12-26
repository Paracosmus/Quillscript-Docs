---
label: Comment
icon: "../../static/img/icons/comment.svg"
order: 1
---
# Comment

Comment lines are ignored by the Lexer and discarded on parsing time. They are useful for adding comments, notes, and general reminders directly to your script.

- A comment statement starts with a **// (_Double Dash_)**, immediately followed by a whitespace.

```q #1,4,7
// Ask the player for character name
$ MyCustomFunction | Stop

// Store character name variable
$ name = {$MyCustomFunctionReturnValue}

// Go to village
-> VillageEntrance

```

---

## <span class="comment">Inline Comment</span>
An inline comment is a comment within another statement line. It is set the same way as a line comment. Be aware that anything after an inline comment opening, is ignored by the parser.

```q #
- Dennis  // Inline comment
  Hello!  // Inline comment

$ gold = 10 // main currency

-> Race | ? {speed} > 5  // Go to race if fast enough
```

---

## <span class="comment">Header Comment</span>
If a [free text](../free-text/) line is set before any other statement in script, these lines are called header comments and differ from usual comments because they don't have a comment marker. They are also ignored and discarded by the parser.

```q #1-4
SCENE 1 - PILOT
Subtitle

Scene description.

- Alice
  First dialogue

// Comment line.
```

---

## <span class="comment">Section</span>
Sections are organizational brackets with no impact on how your script runs. Their goal is to help writers better organize sections of the story without the need for any workarounds.

They also allow you to use the folding feature in most editors, like <a href="https://code.visualstudio.com/" target="_blank">Visual Studio Code</a>.

You start a section with a line containing a single { (Open Bracket) and end it with another line containing a single } (Close Bracket).

```q #1,8
{
  - Bob
    Hi, Alice! How are you?

  - Alice
    Hi, Bob! I'm fine.
    Thank you!
}
```

---
