---
label: Subsystem
icon: container
order: 1
---
# Subsystem

The Quillscript Subsystem is an <a href="https://docs.unrealengine.com/latest/ProgrammingAndScripting/Subsystems/" target="_blank">Unreal Engine's Game Instance Subsystem</a>. This object
manages the plugin as a hole, it holds state properties, and stores Quillscript's data.

---

## Data Storage
The Quillscript Subsystem centralizes all Quillscript relevant data in a single object.

### Variables
Quillscript variables are stored here as a map of key-value. The Key is of type Name, and the value is of type Text. The value is marked as a non-cultural variant by default.

### History
The Quillscript history stores relevant data from scripts. Primarily the number of times this script played and the Save State list containing the sequence of statements played when this script was run.

### References
This is where Quillscript stores the map of object references to use in script.

---

## Events
The Subsystem also centralizes some important assignable events.

### On Script Play
This event fires when a script starts to play.

+++Blueprint
![](../../static/img/examples/on_script_play.png)
+++C++
```cpp
#include "Core/QuillscriptSubsystem.h"
...

if (const TObjectPtr<UQuillscriptSubsystem> Subsystem{ WorldContextObject->GetWorld()->GetGameInstance()->GetSubsystem<UQuillscriptSubsystem>() })
    Subsystem->OnScriptPlay.AddDynamic(this, &UMyObject::ScriptPlay);
```

```cpp
void UMyObject::ScriptPlay(AQuillscriptInterpreter* Interpreter)
{
    // Implementation.
}
```
+++

### On Script End
This event fires when a script finishes to play.

+++Blueprint
![](../../static/img/examples/on_script_end.png)
+++C++
```cpp
#include "Core/QuillscriptSubsystem.h"
...

if (const TObjectPtr<UQuillscriptSubsystem> Subsystem{ WorldContextObject->GetWorld()->GetGameInstance()->GetSubsystem<UQuillscriptSubsystem>() })
    Subsystem->OnScriptEnd.AddDynamic(this, &UMyObject::ScriptEnd);
```

```cpp
void UMyObject::ScriptEnd(FName ScriptId)
{
    // Implementation.
}
```
+++

### On Notified
This event fires when the Interpreter's [Notify built-in function](../../language/command/built-in-functions.md) is called from script or code.

+++Script
```q
$ Notify Message
$ Notify point,data,round
$ Notify 'Hello world!'

```
+++Blueprint
![](../../static/img/examples/on_notified.png)
+++C++
```cpp
#include "Core/QuillscriptSubsystem.h"
...

if (const TObjectPtr<UQuillscriptSubsystem> Subsystem{ WorldContextObject->GetWorld()->GetGameInstance()->GetSubsystem<UQuillscriptSubsystem>() })
    Subsystem->OnNotified.AddDynamic(this, &UMyObject::Notified);
```

```cpp
void UMyObject::Notified(FString Message)
{
    // Implementation.
}
```

```cpp
#include "Core/QuillscriptAsset.h"
#include "Utils/Quill.h"
...

const TObjectPtr<UQuillscriptAsset> Script{ UQuill::GetScriptById("MyScriptId") };
const TObjectPtr<AQuillscriptInterpreter> Interpreter{ UQuill::PlayScript(this, Script) };

Interpreter->Notify("Message");
```
+++

!!!
This event is intended as an easy built-in method to pass string data from script to code. It is not intended as a general purpose, nor to be the only approach to pass data, and it is recommended, for most cases, to create events and functions more suitable for the data type and situation.
!!!

### On Variable Set
This event fires when a variable is created, its value is changed, or a variable is deleted.

+++Blueprint
![](../../static/img/examples/on_variable_set.png)
+++C++
```cpp
#include "Core/QuillscriptSubsystem.h"
...

if (const TObjectPtr<UQuillscriptSubsystem> Subsystem{ WorldContextObject->GetWorld()->GetGameInstance()->GetSubsystem<UQuillscriptSubsystem>() })
    Subsystem->OnVariableSet.AddDynamic(this, &UMyObject::VariableSet);
```

```cpp
void UMyObject::VariableSet(FName VariableName, FText OldValue, FText NewValue)
{
    // Implementation.
}
```
+++

---
