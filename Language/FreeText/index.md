---
label: Free Text
icon: typography
order: 1
---
# Free Text

Syntax Highlighting Test


```q
SCENE 1 - Inn

- . | #tag1 | #tag2 | #tag3 #tag4
	Hello!
- .
	Welcome to <img id="logo"></> <info>Quillscript Plugin</> example project.
	This project is a quick sample of how Quillscript works.
- .
	This text is written using <data tooltip="Our custom scripting language tailored for dialogues">Quillscript Language</>, as any other dialogue in this project.
- .
	You can find the source script files in the <i>Scripts</> folder.
	Check the <b>Level Blueprint</>((1000ms)) and <b>'/Sample/DummyBP'</> Blueprint,((1s)) to see how this is set up.
  {quest_completed}
- .
{
  - Innkeeper
    Do you want to rent a room?
}

* Yes, please.
* No, thank-you. // teste

@ FirstLabel

-> Finish

// Quillscript variable handling
$ flag = on

// Function call
$ Play 1

? if: {quest_completed} == on

~ define header Bob | ? {height} < 1.8

```
