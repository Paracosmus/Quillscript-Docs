---
label: Quill
icon: paintbrush
order: 4
---
# Quill
> Quillscript Function Library

This [Blueprint Function Library](https://dev.epicgames.com/documentation/unreal-engine/blueprint-function-libraries-in-unreal-engine) offers a set of specialized tools and features for Quillscript related tasks, enabling efficient coding, automation, and customization within your Quillscript-powered projects.

---

## <span class="dialogue">Script</span>

[//]: <> (=========================================================================================)

:::api
### Play Script

Initiate the execution of a Quillscript asset.

```rust !#1-2 Parameters
WorldContextObject: ref
Script: ref[QuillscriptAsset]
(Omittable) StartingLabel: Name
(Omittable) Target: ref            // Object referenced by this Script as {&Target}
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
// Get a script reference.
$ ^Quillscript.Quill.GetScriptById MyScriptId

// Play script.
$ ^Quillscript.Quill.PlayScript {&ReturnValue}

// End current script. (Optional)
$ End

```
Notice that this process produces the same result as the <span class="command">$ Travel</span> built-in function and is useful only if you need extra control of the code behavior or order.
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/1ulnr4ow/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Quill.h"
...

UQuill::PlayScript(WorldContextObject, UQuill::GetScriptById("MyScriptId"));
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Play Script Using Custom Settings

Play the given script using a custom set of settings passed as a parameter to this function. It allows you to fine-tune the behavior of the script execution according to your specific requirements.

```rust !#1-3 Parameters
WorldContextObject: ref
Script: ref[QuillscriptAsset]
Settings: ScriptSettings
(Omittable) StartingLabel: Name
(Omittable) Target: ref            // Object referenced by this Script as {&Target}
```

==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/32l7f9vk/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Quill.h"
...

// Configure custom settings.
FScriptSettings Settings;
Settings.EnableInputDuring = EPicker::No;
Settings.ShowMouseCursorAfter = EPicker::Yes;

// Play script using custom settings.
UQuill::PlayScriptUsingCustomSettings(
    WorldContextObject,
    UQuill::GetScriptById("MyScriptId"),
    Settings
);
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Start Script

Same as [Play Script](#play-script) but clears any previous script history to ensure a fresh start.

```rust !#1-2 Parameters
WorldContextObject: ref
Script: ref[QuillscriptAsset]
(Omittable) StartingLabel: Name
(Omittable) Target: ref            // Object referenced by this Script as {&Target}
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
// Get a script reference.
$ ^Quillscript.Quill.GetScriptById MyScriptId

// Start script.
$ ^Quillscript.Quill.StartScript {&ReturnValue}

// End current script. (Optional)
$ End

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/3nvpq675/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Quill.h"
...

UQuill::StartScript(WorldContextObject, UQuill::GetScriptById("MyScriptId"));
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Start Script Using Custom Settings

Same as [Play Script Using Custom Settings](#play-script-using-custom-settings) but clears any previous script history to ensure a fresh start.

```rust !#1-3 Parameters
WorldContextObject: ref
Script: ref[QuillscriptAsset]
Settings: ScriptSettings
(Omittable) StartingLabel: Name
(Omittable) Target: ref            // Object referenced by this Script as {&Target}
```

==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/hxev1qvc/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Quill.h"
...

// Configure custom settings.
FScriptSettings Settings;
Settings.EnableInputDuring = EPicker::No;
Settings.ShowMouseCursorAfter = EPicker::Yes;

// Start script using custom settings.
UQuill::StartScriptUsingCustomSettings(
    WorldContextObject,
    UQuill::GetScriptById("MyScriptId"),
    Settings
);
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Resume Script

Continue the execution of a Quillscript from the last saved state entry in the script's history. It enables you to pick up the script where it left off, making it useful for scenarios where you need to maintain script continuity or when the game was saved during a script play and need to continue from that point.

```rust !#1-2 Parameters
WorldContextObject: ref
Script: ref[QuillscriptAsset]
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
// Get a script reference.
$ ^Quillscript.Quill.GetScriptById MyScriptId

// Play script.
$ ^Quillscript.Quill.ResumeScript {&ReturnValue}

// End current script. (Optional)
$ End

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/3rpxv0wp/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Quill.h"
...

UQuill::ResumeScript(WorldContextObject, UQuill::GetScriptById("MyScriptId"));
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Parse Script

Takes a Quillscript language valid string as input and converts it into a Quillscript asset. This is particularly useful when you need to dynamically create or modify scripts at runtime, or when you allow modders or user to create their own scripts.

You can also specify a permission mode to control the script's behavior. See [Permissions](../objects/script.md#permissions) for more details.

```rust !#1 Parameters
Text: string
(Omittable) Permission: PermissionMode        [ All, Safe, Sandbox ]
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
// Get a valid Quillscript language string.
$ :QuillscriptLanguageValidString := '$ x = 1'

// Create script object reference.
$ ^Quillscript.Quill.ParseScript {:QuillscriptLanguageValidString}

// Play created script.
$ ^Quillscript.Quill.PlayScript {&ReturnValue}

// End current script. (Optional)
$ End

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/rmm-pt77/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Quill.h"
...

const TObjectPtr<UQuillscriptAsset> Script{ UQuill::ParseScript(QuillscriptLanguageValidString, EPermissionMode::Sandbox) };
UQuill::PlayScript(WorldContextObject, Script);
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Get Scripts

Retrieves a list of all available Quillscript script assets within your project. This can be useful when you need to access and manage multiple scripts programmatically.

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
$ ^Quillscript.Quill.GetScripts

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/3lyor2zq/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Quill.h"
...

TArray<UQuillscriptAsset*> Scripts{ UQuill::GetScripts() };

for (auto Script : Scripts)
{
    // Implementation.
}
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Get Script by Path

Retrieve a specific Quillscript asset by providing its path within your project. This function simplifies script asset retrieval, making it easy to access the script you need for execution or manipulation.

```rust !#1 Parameters
Path: string
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
// Get a script reference.
$ ^Quillscript.Quill.GetScriptByPath /Game/Path/To/MyScript.MyScript

// Play script.
$ ^Quillscript.Quill.PlayScript {&ReturnValue}

// End current script. (Optional)
$ End

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/b15w4531/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Quill.h"
...

const TObjectPtr<UQuillscriptAsset> Script{ UQuill::GetScriptByPath("/Game/Path/To/MyScript.MyScript") };
UQuill::PlayScript(WorldContextObject, Script);
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Get Script by Id

Retrieve a Quillscript asset by its unique identifier (Id). Keep in mind that this function may have performance implications in projects with a large number of assets. Use it when you need to specifically locate a script by its Id.

```rust !#1 Parameters
Id: name
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
// Get a script reference.
$ ^Quillscript.Quill.GetScriptById MyScriptId

// Play script.
$ ^Quillscript.Quill.PlayScript {&ReturnValue}

// End current script. (Optional)
$ End

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/ds2mnsuz/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Quill.h"
...
const TObjectPtr<UQuillscriptAsset> Script{ UQuill::GetScriptById("MyScriptId") };
UQuill::PlayScript(WorldContextObject, Script);
```
===
:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Get a Quillscript asset )
[comment]: <> ( By Id:				    @MyScript )
[comment]: <> ( By Path:				/Game/Folder/MyScript.MyScript )
[comment]: <> ( By Script Reference:    {&/Game/Folder/MyScript.MyScript} )
[comment]: <> ( static UQuillscriptAsset* FindScript | FString ScriptRef )


:::api
### Find Script

Get a Quillscript asset by its reference, which can be either an Id, a path, or a script reference.

```rust !#1 Parameters
ScriptRef: string
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
$ ^Quillscript.Quill.FindScript @MyScript

$ ^Quillscript.Quill.FindScript /Game/Folder/MyScript.MyScript

$ ^Quillscript.Quill.FindScript {&/Game/Folder/MyScript.MyScript}

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/irhgj-74/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Quill.h"
...

TObjectPtr<UQuillscriptAsset> ScriptById{ UQuill::FindScript("@MyScript") };
TObjectPtr<UQuillscriptAsset> ScriptByPath{ UQuill::FindScript("/Game/Folder/MyScript.MyScript") };
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Is Script Playing

Checks whether a specified Quillscript script is currently playing.

```rust !#1 Parameters
WorldContextObject: ref
Script: ref[QuillscriptAsset]
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
$ ^Quillscript.Quill.GetScriptById MyScriptId
$ ^Quillscript.Quill.IsScriptPlaying {&ReturnValue}

if: {$ReturnValue} == on

    // Do something

endif

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/lquq2s2q/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Quill.h"
...
const TObjectPtr<UQuillscriptAsset> Script{ UQuill::GetScriptById("MyScriptId") };

if (UQuill::IsScriptPlaying(WorldContextObject, Script))
{
    // Implementation
}
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Is Any Script Playing

Checks whether any Quillscript script is currently playing.

```rust !#1 Parameters
WorldContextObject: ref
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
$ ^Quillscript.Quill.IsAnyScriptPlaying

if: {$ReturnValue} == on

    // Do something

endif

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/z2-akkyt/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Quill.h"
...
if (UQuill::IsAnyScriptPlaying(WorldContextObject))
{
    // Implementation
}
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Make Permissions List

Generates a list of script permissions based on the specified permission mode. This function is helpful when you need to create a list of permissions for your scripts programmatically, allowing you to control the behavior of the scripts according to your permission requirements.

See [Permissions](../objects/script.md#permissions) for more details.

```rust !#1 Parameters
PermissionMode: PermissionMode                [ All, Safe, Sandbox ]
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
// Get a script reference.
$ ^Quillscript.Quill.MakePermissionsList Sandbox

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/dp9-3jxf/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Quill.h"
...

TArray<EPermission> Permissions{ UQuill::MakePermissionsList(EPermissionMode::Sandbox) };
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Set Script Play Counter

Set the script **Times Played** counter value.

```rust !#1-3 Parameters
WorldContextObject: ref
Script: ref[QuillscriptAsset]
TimesPlayed: i32
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
// Get a script reference.
$ ^Quillscript.Quill.GetScriptByPath /Game/Path/To/MyScript.MyScript

// Set counter value.
$ ^Quillscript.Quill.SetScriptPlayCounter {&ReturnValue} 5

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/ym1w258m/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Quill.h"
...

const TObjectPtr<UQuillscriptAsset> Script{ UQuill::GetScriptByPath("/Game/Path/To/MyScript.MyScript") };
UQuill::SetScriptPlayCounter(WorldContextObject, Script, 5);
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Reset Script Play Counter

Reset the script **Times Played** counter back to 0.

```rust !#1-2 Parameters
WorldContextObject: ref
Script: ref[QuillscriptAsset]
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
// Get a script reference.
$ ^Quillscript.Quill.GetScriptByPath /Game/Path/To/MyScript.MyScript

// Set counter value.
$ ^Quillscript.Quill.ResetScriptPlayCounter {&ReturnValue}

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/oeppl6rt/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Quill.h"
...

const TObjectPtr<UQuillscriptAsset> Script{ UQuill::GetScriptByPath("/Game/Path/To/MyScript.MyScript") };
UQuill::ResetScriptPlayCounter(WorldContextObject, Script);
```
===
:::
<br>


---

## <span class="dialogue">Interpreter</span>


[//]: <> (=========================================================================================)

:::api
### Create Interpreter

Spawn an interpreter actor. It is recommended to use this method instead of manually spawning an interpreter actor.

```rust !#1 Parameters
WorldContextObject: ref
(Omittable) InterpreterClass: SubclassOf[QuillscriptInterpreter]
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
$ ^Quillscript.Quill.CreateInterpreter

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/lgn5zn9v/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Quill.h"
...

const TSubclassOf<AQuillscriptInterpreter> InterpreterClass{ LoadClass<AQuillscriptInterpreter>(nullptr, TEXT("/Game/Path/To/MyInterpreter.MyInterpreter_C")) };
const TObjectPtr<AQuillscriptInterpreter> Interpreter{ UQuill::CreateInterpreter(WorldContextObject, InterpreterClass) };
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Get Interpreters

Retrieve all instantiated interpreter objects in the specified world context.

```rust !#1 Parameters
WorldContextObject: ref
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
$ ^Quillscript.Quill.GetInterpreters

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/zddcvf3n/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Quill.h"
...

TArray<AQuillscriptInterpreter*> Interpreters{ UQuill::StartScript(WorldContextObject) };

for (auto Interpreter : Interpreters)
{
    // Implementation.
}
```
===
:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Get player owned Network object. )
[comment]: <> ( static AQuillscriptNetwork* GetNetwork | const UObject* WorldContextObject )


:::api
### Get Network

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


---

## <span class="dialogue">Variables</span>


[//]: <> (=========================================================================================)

:::api
### Quillscript Variable Exists

Check the existence of a Quillscript variable with a specified name. This function is particularly useful when you need to determine whether a specific variable is defined.

```rust !#1 Parameters
WorldContextObject: ref
VariableName: name
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
// Store result in {$ReturnValue}.
$ ^Quillscript.Quill.QuillscriptVariableExists VariableName

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/xetocjea/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Quill.h"
...

if (UQuill::QuillscriptVariableExists(WorldContextObject, FName("VariableName")))
{
    // Implementation.
}
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Get Quillscript Variable

Retrieves the value of a Quillscript variable with the specified name. If the variable does not exist, it returns "off" as a default value.

```rust !#1-2 Parameters
WorldContextObject: ref
VariableName: name
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
// Store result in {$ReturnValue}.
$ ^Quillscript.Quill.GetQuillscriptVariable VariableName

```
Notice that this produces the same result as using the variable directly like
`$ x = {VariableName}`

But this is useful to get a variable using a dynamic name.
```q
$ ^Quillscript.Quill.GetQuillscriptVariable {dynamicName}

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/9j94tmxj/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Quill.h"
...

// Macro (Only inside an UObject method)
FString VariableValue{ VAR("VariableName") };

// Function call.
FString VariableValue{ UQuill::GetQuillscriptVariable(WorldContextObject, FName("VariableName")) };
```
===
:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Get the value of a Quillscript variable as number. )
[comment]: <> ( ! on = 1; off = 0; Text = 0)
[comment]: <> ( static double GetQuillscriptNumber | const UObject* WorldContextObject, const FName VariableName )


:::api
### Get Quillscript Number

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Get the value of a Quillscript variable as switch. )
[comment]: <> ( ! on = on; true = on; 1 = on; everything else = off)
[comment]: <> ( static bool GetQuillscriptSwitch | const UObject* WorldContextObject, const FName VariableName )


:::api
### Get Quillscript Switch

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Set the value of a Quillscript variable. Create it if it does not exists. )
[comment]: <> ( static void SetQuillscriptVariable | const UObject* WorldContextObject, const FName VariableName, FText Value )


:::api
### Set Quillscript Variable

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( static void SetQuillscriptVariables | const UObject* WorldContextObject, const TMap<FName, FText> Variables )


:::api
### Set Quillscript Variables

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( static void IncrementQuillscriptVariable | const UObject* WorldContextObject, const FName VariableName )


:::api
### Increment Quillscript Variable

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( static bool DeleteQuillscriptVariable | const UObject* WorldContextObject, const FName Name )


:::api
### Delete Quillscript Variable

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( static FString ReplaceQuillscriptVariables | const UObject* WorldContextObject, const FString String )


:::api
### Replace Quillscript Variables

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( static void SetTemporaryVariables | const UObject* WorldContextObject, const TMap<FName, FText> Variables )


:::api
### Set Temporary Variables

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( static bool RenameQuillscriptVariable | const UObject* WorldContextObject, const FName OldName, const FName NewName )


:::api
### Rename Quillscript Variable

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( static bool IsConstant | const UObject* WorldContextObject, const FName Name )


:::api
### Is Constant

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Find all global variables and constants declarations in script assets. )
[comment]: <> ( ! This function can be slow if too many script lines to check. )
[comment]: <> ( static TArray<FName> GetAllProjectGlobals )


:::api
### Get All Project Globals

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( static void AddScriptReference | const UObject* WorldContextObject, const FName Name, UObject* Reference )


:::api
### Add Script Reference

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Remove all occurrences of the given pointer from script references map. )
[comment]: <> ( ! Not efficient with big reference maps. )
[comment]: <> ( static bool RemoveScriptReference | const UObject* WorldContextObject, const UObject* Reference)


:::api
### Remove Script Reference

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( static bool RemoveScriptReferenceByName | const UObject* WorldContextObject, const FName Name )


:::api
### Remove Script Reference by Name

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Remove all null pointer from script references map. )
[comment]: <> ( ! Not efficient with big reference maps. )
[comment]: <> ( static void ClearNullScriptReferences | const UObject* WorldContextObject )


:::api
### Clear Null Script References

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

:::api
### Register Variable Modifier

Register a variable modifier.

When a Quillscript variable value is requested, the delegate event is played before retrieving the value, allowing the code to modify the variable value beforehand or to play some required code.

```rust !#1-2 Parameters
VariableName: name
Delegate: event
```

==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/msedikbn/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Quill.h"
...

FVariableGetDelegate OnVariableGet;
OnVariableGet.BindDynamic(MyObject, &UMyObject::MyFunction);

UQuill::RegisterVariableModifier(this, "HasCheckpointFinished", OnVariableGet);
```
```cpp
void UMyObject::MyFunction(const FName& VariableName, const FString& VariableValue)
{
    // Implementation.
}
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Unregister Variable Modifier

Unregister a variable modifier.

```rust !#1 Parameters
VariableName: name
```

==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/_fkpkbmi/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Quill.h"
...

UQuill::UnregisterVariableModifier(this, "VariableName")
```
===
:::


---

## <span class="dialogue">Save</span>


[//]: <> (=========================================================================================)

[comment]: <> ( Clear all Quillscript variables and script history. )
[comment]: <> ( static void RefreshQuillscript | const UObject* WorldContextObject )


:::api
### Refresh Quillscript

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

:::api
### Save Game and Story to Slot

This function behaves the same as the native [Save Game to Slot](https://docs.unrealengine.com/latest/BlueprintAPI/SaveGame/SaveGametoSlot/), but additionally injects Quillscript data to the save game file.

Saves game data and Quillscript data to a specified save slot. The function returns true if the save operation is successful, and false otherwise.

```rust !#1-4 Parameters
WorldContextObject: ref
SaveGameObject: ref[SaveGame]
SlotName: string
UserIndex: number
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
// Save game and Quillscript data to 'MySlot'.
$ ^Quillscript.Quill.SaveGameAndStoryToSlot {&SaveGame} "MySlot" 0

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/aury0c-9/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Quill.h"
...

TObjectPtr<UMySaveGame> SaveGame{ Cast<UMySaveGame>(UGameplayStatics::CreateSaveGameObject(UMySaveGame::StaticClass())) };
UQuill::SaveGameAndStoryToSlot(WorldContextObject, SaveGame, "MySlot", 0);
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Load Game and Story from Slot

This function behaves the same as the native [Load Game from Slot](https://docs.unrealengine.com/latest/BlueprintAPI/SaveGame/LoadGamefromSlot/), but additionally extracts Quillscript data from the save game file and update Quillscript subsystem with the extracted data.

Returns a Save Game object containing the loaded data.

```rust !#1-3 Parameters
WorldContextObject: ref
SlotName: string
UserIndex: number
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
// Load game and Quillscript data from 'MySlot'.
$ ^Quillscript.Quill.LoadGameAndStoryFromSlot "MySlot" 0

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/-qfrj-z8/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Quill.h"
...

UQuill::LoadGameAndStoryFromSlot(WorldContextObject, "MySlot", 0);
```
===
:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( static USaveGame* ResumeGameAndStoryFromSlot | const UObject* WorldContextObject, const FString SlotName, const int32 UserIndex )


:::api
### Resume Game and Story from Slot

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


---

## <span class="dialogue">Pipes</span>


[//]: <> (=========================================================================================)

[comment]: <> ( static FString EvaluateQuillscriptExpression | const FString& Expression )


:::api
### Evaluate Quillscript Expression

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( static bool PickerToBoolean | const EPicker Picker )


:::api
### Picker to Boolean

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>

---
