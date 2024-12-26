---
label: Free Text
icon: typography
order: 1
---
# Free Text

Any free text line found in your script (with not Quillscript syntax symbol in the beginning of the line), is attached as a text line to the previous statement. That's how dialogues and multiline options set their text lines.


```q Dialogue text line
- Speaker Name
  Text line.
```


```q Option multiline text
* *
  Multiline
  option.
```


```q Label display name
@ LabelName
  Label Display Name
```

!!!
Free text lines in the beginning of a script are [Header Comments](../comment/index.md#header-comment).
!!!

---
