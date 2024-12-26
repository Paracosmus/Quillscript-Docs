---
label: Quill
icon: paintbrush
order: 4
---
# Quill
> Quillscript Function Library

This library offers a set of specialized tools and features for Quillscript Plugin users, enabling efficient coding, automation, and customization within your Quillscript-powered projects.

---

## <span class="dialogue">Script</span>

[//]: <> (=========================================================================================)

[comment]: <> ( Play the given Quillscript script asset. )
[comment]: <> ( static AQuillscriptInterpreter* PlayScript | const UObject* WorldContextObject, UQuillscriptAsset* Script, const FName StartingLabel = NAME_None, UObject* Target = nullptr )


:::api
### Play Script

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Play script from start using custom settings instead of script settings. )
[comment]: <> ( static AQuillscriptInterpreter* PlayScriptUsingCustomSettings | const UObject* WorldContextObject, UQuillscriptAsset* Script, FScriptSettings Settings, const FName StartingLabel = NAME_None, UObject* Target = nullptr )


:::api
### Play Script Using Custom Settings

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Play script from start. Delete any previous script history. )
[comment]: <> ( static AQuillscriptInterpreter* StartScript | const UObject* WorldContextObject, UQuillscriptAsset* Script, const FName StartingLabel = NAME_None, UObject* Target = nullptr )


:::api
### Start Script

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Play script from start using custom settings instead of script settings. Delete any previous script history. )
[comment]: <> ( static AQuillscriptInterpreter* StartScriptUsingCustomSettings | const UObject* WorldContextObject, UQuillscriptAsset* Script, FScriptSettings Settings, const FName StartingLabel = NAME_None, UObject* Target = nullptr )


:::api
### Start Script Using Custom Settings

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Play script from last history's save state entry. )
[comment]: <> ( Used when the game was saved during a script play, and resume from that saved point. )
[comment]: <> ( static AQuillscriptInterpreter* ResumeScript | const UObject* WorldContextObject, UQuillscriptAsset* Script )


:::api
### Resume Script

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Parse a Quillscript text into a script object. )
[comment]: <> ( static UQuillscriptAsset* ParseScript | const FString Text, const EPermissionMode Permission = EPermissionMode::Safe )


:::api
### Parse Script

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Get a list of all Quillscript script assets. )
[comment]: <> ( static TArray<UQuillscriptAsset*> GetScripts )


:::api
### Get Scripts

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Get a Quillscript asset by path. |/Game/Folder/MyScript.MyScript| )
[comment]: <> ( static UQuillscriptAsset* GetScriptByPath | const FString& Path )


:::api
### Get Script by Path

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Get a Quillscript asset by it's Id. )
[comment]: <> ( ! This function may be slow on large project with thousands of assets. )
[comment]: <> ( static UQuillscriptAsset* GetScriptById | const FName Id )


:::api
### Get Script by Id

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

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

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Check if the given Quillscript script is currently playing. )
[comment]: <> ( static bool IsScriptPlaying | const UObject* WorldContextObject, const UQuillscriptAsset* Script )


:::api
### Is Script Playing

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Check if any Quillscript script is currently playing. )
[comment]: <> ( static bool IsAnyScriptPlaying | const UObject* WorldContextObject )


:::api
### Is Any Script Playing

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Make a list with all script permissions. )
[comment]: <> ( static TArray<EPermission> MakePermissionsList | const EPermissionMode PermissionMode )


:::api
### Make Permissions List

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Reset the script 'Times Played' counter. )
[comment]: <> ( static void SetScriptPlayCounter | const UObject* WorldContextObject, const UQuillscriptAsset* Script, const int32 TimesPlayed )


:::api
### Set Script Play Counter

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Set the script 'Times Played' counter. )
[comment]: <> ( static void ResetScriptPlayCounter | const UObject* WorldContextObject, const UQuillscriptAsset* Script )


:::api
### Reset Script Play Counter

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


---

## <span class="dialogue">Interpreter</span>


[//]: <> (=========================================================================================)

[comment]: <> ( Spawn an interpreter actor. )
[comment]: <> ( Use this method instead of spawning it manually. )
[comment]: <> ( static AQuillscriptInterpreter* CreateInterpreter | const UObject* WorldContextObject, TSubclassOf<AQuillscriptInterpreter> InterpreterClass = nullptr )


:::api
### Create Interpreter

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Get all instantiated interpreter objects. )
[comment]: <> ( static TArray<AQuillscriptInterpreter*> GetInterpreters | const UObject* WorldContextObject )


:::api
### Get Interpreters

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

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

[comment]: <> ( static bool QuillscriptVariableExists | const UObject* WorldContextObject, const FName VariableName )


:::api
### Quillscript Variable Exists

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Get the value of a Quillscript variable. Return "off" if does not it exists. )
[comment]: <> ( static FString GetQuillscriptVariable | const UObject* WorldContextObject, const FName VariableName )


:::api
### Get Quillscript Variable

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

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

[comment]: <> ( static bool SaveGameAndStoryToSlot | const UObject* WorldContextObject, USaveGame* SaveGameObject, const FString SlotName, const int32 UserIndex )


:::api
### Save Game and Story to Slot

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( static USaveGame* LoadGameAndStoryFromSlot | const UObject* WorldContextObject, const FString SlotName, const int32 UserIndex )


:::api
### Load Game and Story from Slot

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

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
