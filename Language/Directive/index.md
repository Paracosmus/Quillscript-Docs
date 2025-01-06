---
label: Directive
icon: "../../static/img/icons/directive.svg"
order: 4
---
# Directive

Directives are tasks that can execute either during runtime or before a Script starts. They are intended for automation and do pre-processing tasks.

- A Directive statement starts with a **~ (_Tilde_)**, immediately followed by a space and the directive name.

---

## <span class="directive">Start</span>
Defines a different starting point for this script.

By default, Quillscript scripts start at the beginning of the text file. With this directive, you can set a custom starting point.

```q #
- Hank
  Jump this.

// This script actually starts here.
~ start

- Hank
  This is the first dialogue.
```

If you have the **Keep Script History** setting enabled in Quillscript Settings, you can add an index to multiple usages of the Start Directive. The Interpreter will start the script at index 1 the first time this script is played, at index 2 on the second play, and so on.

```q #
~ start 1
- Matthew
  Hello, I'm Matthew.

~ start 2
- Matthew
  Can I help you?
```

---

## <span class="directive">Define</span>
Replaces all occurrences of a pre-defined string during parsing time.

```q #
~ define header Bob | ? {height} < 1.8

$ height = 1.5

- [header]
  Hello.
- [header]
  I'm short.
```

It is also possible to add parameters to the Define directive separated from the definition name with a : (colon). Any occurrence of those parameters will be replaced by their equivalent in the directive usage.

```q #
~ define path:name "{&/Game/Assets/Characters/name.name}"

$ Sprite Alice
$ &Alice.Show [path:Alice_Idle]
// Replaced with {&/Game/Assets/Characters/Alice_Idle.Alice_Idle}
```

Or multiple parameters separated by ; (semi-colon)

```q #
~ define path:folder;name "{&/Game/Assets/Characters/folder/name.name}"

$ Sprite Bob
$ &Bob.Show [path:Bob;Idle]
// Replaced with {&/Game/Assets/Characters/Bob/Idle.Idle}
```

---

## <span class="directive">Replace</span>
Replaces all occurrences of a pre-defined parameter, before the script starts.

```q #
~ replace name Bob
~ replace condition {height} < 1.5

$ height = 1.5

- [name] | ? [condition]
  Hello.

- [name] | ? [condition]
  I'm short.
```

---

## <span class="directive">Include</span>
Inserts the data of a given Quillscript Script asset, at this point, either by id or by path.

To include a Script by id, use the script id starting with a @.

```q
~ include @MyScriptId

```

To include a Script by path, use the script path, simple or complete.

```q
~ include /Game/MyScript.MyScript
~ include /Script/Quillscript.QuillscriptAsset'/Game/MyScript.MyScript'

```

```q #
~ include @MyScriptId

// Insert the content of "MyScript" again, at this position.
~ include @MyScriptId

```

!!!danger
Be aware not to cyclically include one script into another creating an infinite loop.
!!!

---

## <span class="directive">Import</span>
Inserts the data of a given Quillscript Script asset, at the start of this script, only once, either by id or by path.

To import a Script by id, use the script id starting with a @.

```q
~ import @MyScriptId

```

To include a Script by path, use the script path, simple or complete.

```q
~ import /Game/MyScript.MyScript
~ import /Script/Quillscript.QuillscriptAsset'/Game/MyScript.MyScript'

```

```q #
~ import @MyScriptId

// This one is ignored because this script was imported before.
~ import @MyScriptId

```

!!!danger
Be aware not to cyclically include one script into another creating an infinite loop.
!!!

---

## <span class="directive">Inject</span>
Inserts the content of a given label from an external script, at this point, either by id or by path.

To inject a label content by id, use the script id starting with a @.

```q
~ inject @MyScriptId MyLabelName

```

To include a label content by path, use the script path, simple or complete.

```q
~ inject /Game/MyScript.MyScript MyLabelName
~ inject /Script/Quillscript.QuillscriptAsset'/Game/MyScript.MyScript' MyLabelName

```

```q #
~ inject @MyScriptId MyLabelName

// Insert the content of "MyLabelName" again, at this position.
~ inject @MyScriptId MyLabelName

```

!!!danger
Be aware not to cyclically include one script or label into another creating an infinite loop.
!!!

---

## <span class="directive">Checkpoint</span>
This directive halts the execution of the script until a specified condition is met. The Interpreter remains in a waiting state and does not proceed to the next line of code until the condition evaluates to true. The condition is an expression that can be evaluated.

```q
~ checkpoint | ? {myVar} < 10 OR {flat} == on
```

It accepts a number parameter to set the delay in seconds between condition checks, this help to improve performance, it checks every frame otherwise.

```q
~ checkpoint 0.5 | ? {myVar} + 3 < 10 AND {flat} == on
```

It is also possible to concatenate Command statements to execute before each conditions check.

```q
~ checkpoint 0.5 | &Obj.CheckMyCondition | ? {$ReturnValue} == on
```

---
