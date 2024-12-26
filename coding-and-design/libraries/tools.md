---
label: Tools
icon: tools
order: 3
---
# Tools
> Tools Function Library

The **Tools Function Library** is a versatile collection of extra utility functions designed to streamline and simplify common tasks in Unreal Engine game development.

This library is a useful resource for any Unreal Engine project, offering a wide range of functions that provide essential functionality for various game development needs.

---

## <span class="tag">Print</span>


[//]: <> (=========================================================================================)

[comment]: <> ( Print a log message in editor. )
[comment]: <> ( @param	Message )
[comment]: <> ( @param	Owner		Object that called this function. Can be null. )
[comment]: <> ( @param	PrintType	Message type, to change text color accordingly. )
[comment]: <> ( void Log | FString Message, const UObject* Owner = nullptr, const EPrintType PrintType = EPrintType::Log )

:::api
### Log

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

:::api
### Print

Print a message on screen and/or console. (In Development, Debug or Editor mode)

Check your Verbosity setting to select where this message is printed.

```rust !#1 Parameters
Message: string
[Omittable] Owner: ref    // Object that called this function.
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
$ ^Quillscript.Tools.Print Hello
$ ^Quillscript.Tools.Print 'Print this message'
$ ^Quillscript.Tools.Print 'Print this message' {&Script}

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/gvgr4pii/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Tools.h"
...

// Macro (Only inside an UObject method)
PRINT("Print this message" )

// Function call.
UTools::Print("Print this message", MyObject)
```
===

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Print a success message in editor. )
[comment]: <> ( @param	Message )
[comment]: <> ( @param	Owner	Object that called this function. Can be left blank. )
[comment]: <> ( void Success | const FString Message, const UObject* Owner = nullptr )

:::api
### Success

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Print a warning message in editor. )
[comment]: <> ( @param	Message )
[comment]: <> ( @param	Owner	Object that called this function. Can be left blank. )
[comment]: <> ( void Warning | const FString Message, const UObject* Owner = nullptr )

:::api
### Warning

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Print an error message in editor. )
[comment]: <> ( @param	Message )
[comment]: <> ( @param	Owner	Object that called this function. Can be left blank. )
[comment]: <> ( void Error | const FString Message, const UObject* Owner = nullptr )

:::api
### Error

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


---

## <span class="tag">Utilities</span>


[//]: <> (=========================================================================================)

[comment]: <> ( Rename a given object. )
[comment]: <> ( Whitespaces will be removed. )
[comment]: <> ( void RenameObject | UObject* Object, FString NewName )

:::api
### Rename Object

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Try to find a class by path. )
[comment]: <> ( UClass* FindClassByPath | FString Path )

:::api
### Find Class by Path

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( UObject* GetClassDefaultObject | const UClass* Class )

:::api
### Get Class Default Object

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Check if an object has a property with the given name. )
[comment]: <> ( @param Object		Object that owns the property. )
[comment]: <> ( @param PropertyName	Name of the property to find. )
[comment]: <> ( @param Type			Outer parameter to store the property type. Stores 'undefined' if the property is not found. )
[comment]: <> ( @return	Return true if a property with the given name is found. )
[comment]: <> ( bool PropertyExists | UObject* Object, const FName PropertyName, FString& Type )

:::api
### Property Exists

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Get the value as a string, of an object's property. )
[comment]: <> ( @param Object		Object that owns the property. )
[comment]: <> ( @param PropertyName	Name of the property to find. )
[comment]: <> ( @param Type			Outer parameter to store the property type. Stores 'undefined' if the property is not found. )
[comment]: <> ( @return	Return value as a string. )
[comment]: <> ( FString GetPropertyByName | UObject* Object, const FName PropertyName, FString& Type )

:::api
### Get Property by Name

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Set the value as a string of an object's property. )
[comment]: <> ( @param Object		Object that owns the property. )
[comment]: <> ( @param PropertyName	Name of the property to find. )
[comment]: <> ( @param ValueAsString	Value to set, in string format. )
[comment]: <> ( void SetPropertyByName | UObject* Object, const FName PropertyName, const FString ValueAsString )

:::api
### Set Property by Name

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Get the value as a string, of an object's property. )
[comment]: <> ( To Use the property later, it can be converted to the desired type or used as a void*. )
[comment]: <> ( @param Object		Object that owns the property. )
[comment]: <> ( @param PropertyName	Name of the property to find. )
[comment]: <> ( @param Type			Outer parameter to store the property type. Stores 'undefined' if the property is not found. )
[comment]: <> ( @return	Return value as a pointer. )
[comment]: <> ( void* FindPropertyByName | UObject* Object, const FName PropertyName, FString& Type )

:::api
### Find Property by Name

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Set the value as a string of an object's property. )
[comment]: <> ( @param Object		Object that owns the property. )
[comment]: <> ( @param PropertyName	Name of the property to find. )
[comment]: <> ( @param ValuePtr		Value as a void pointer. )
[comment]: <> ( `UTools::InsertPropertyByName | Object, "PropertyName", &AnyDataType` )
[comment]: <> ( or )
[comment]: <> ( `const void* ValuePtr{ &AnyDataType };` )
[comment]: <> ( `UTools::InsertPropertyByName | Object, "PropertyName", ValuePtr` )
[comment]: <> ( void InsertPropertyByName | UObject* Object, const FName PropertyName, const void* ValuePtr )

:::api
### Insert Property by Name

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Call a Target's function by name. )
[comment]: <> ( This is a simplified general usage version of 'Interpreter.CallFunctionOnTarget' )
[comment]: <> ( that does not create Quillscript variables and script references. )
[comment]: <> ( @param WorldContextObject )
[comment]: <> ( @param Target		Object to call the function from. )
[comment]: <> ( @param FunctionName	Name of the function to call. )
[comment]: <> ( @param Parameters	Function entry parameters to pass as strings. The parameters must be in the same order they are declared. )
[comment]: <> ( @return	Return value and outer parameters of the function. )
[comment]: <> ( TMap<FName, FString> CallFunctionByName | UObject* WorldContextObject, UObject* Target, const FName FunctionName, const TArray<FString>& Parameters )

:::api
### Call Function by Name

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Shortcut function to be used inside static methods that have a 'WorldContextObject' parameter. )
[comment]: <> ( If your function has access to 'HasAuthority' by other means, use those instead. )
[comment]: <> ( Can also be used with the macro 'HAS_AUTHORITY'. )
[comment]: <> ( bool HasAuthority | const UObject* WorldContextObject )

:::api
### Has Authority

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Check if a module/plugin is loaded. )
[comment]: <> ( bool IsModuleLoaded | const FName ModuleName )

:::api
### Is Module Loaded

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Generate a random string of characters including numbers and symbols. )
[comment]: <> ( FString GenerateRandomString | const uint8 Size = 8, const bool bLetters = true, const bool bNumbers = true, const bool bSymbols = false )

:::api
### Generate Random String

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Get a Level transition option. )
[comment]: <> ( @param	WorldContextObject )
[comment]: <> ( @param	Key					Option key. )
[comment]: <> ( @param	Value				Receive option value. )
[comment]: <> ( @return	True, if the option key exists. )
[comment]: <> ( bool RetrieveOption | const UObject* WorldContextObject, const FString& Key, FString& Value )

:::api
### Retrieve Option

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( TArray<FString> SortStringsAlphabetically | TArray<FString> Strings )

:::api
### Sort Strings Alphabetically

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Load a String Table if it is not. )
[comment]: <> ( void RegisterStringTable | const FName StringTablePath )

:::api
### Register String Table

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Find the String Table key of a given Text variable. )
[comment]: <> ( FString FindStringTableKey | const FText& Text, FName& StringTableId )

:::api
### Find String Table Key

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Create a list with all variable names in a string. )
[comment]: <> ( TArray<FString> GetVariablesInString | FString String )

:::api
### Get Variables in String

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Get the length of a container as string  | Array, Set, Map. )
[comment]: <> ( This is useful to get the length of an array in a Quillscript script, use the engine methods for all other cases. )
[comment]: <> ( int32 Length | FString ContainerAsString )

:::api
### Length

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


---

## <span class="tag">Metadata</span>


[//]: <> (=========================================================================================)

[comment]: <> ( Return the project name set in the 'Edit > Project Settings > Project > Description > Project Name' field. )
[comment]: <> ( FString GetProjectName )

:::api
### Get Project Name

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Return the project version set in the 'Edit > Project Settings > Project > Description > Project Version' field. )
[comment]: <> ( FString GetProjectVersion )

:::api
### Get Project Version

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Return the company name set in the 'Edit > Project Settings > Project > Description > Company Name' field. )
[comment]: <> ( FString GetCompanyName )

:::api
### Get Company Name

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


---

## <span class="tag">Assets</span>


[//]: <> (=========================================================================================)

[comment]: <> ( Mark the given asset as dirty. )
[comment]: <> ( void MarkAssetDirty | const UObject* Asset )

:::api
### Mark Asset Dirty

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Save the given asset to disk, overriding the previous asset data. )
[comment]: <> ( void SaveAsset | UObject* Asset )

:::api
### Save Asset

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


---

## <span class="tag">Files</span>

[comment]: <> ( Get all save games' slot names in '/Saved/SaveGames' folder, without the '.sav' extension | filename only |. )
[comment]: <> ( @return List of found save games' slot names. )
[comment]: <> ( TArray<FString> GetAllSaveGameSlotNames )

:::api
### Get All Save Game Slot Names

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Save content to a text file. )
[comment]: <> ( @param	FileName		File name to save. Ex.: "Notes.txt", "Folder/SubFolder/MyTextFile.ini" )
[comment]: <> ( @param	FileContent		Text content to save )
[comment]: <> ( @param	BaseDirectory	Base directory to save the file. )
[comment]: <> ( @return	Did saved )
[comment]: <> ( bool SaveToTextFile | const FString FileName, const FString FileContent, const EDirectory BaseDirectory = EDirectory::Custom )

:::api
### Save to Text File

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Load a text file content. )
[comment]: <> ( @param	FileContent		Variable to store the loaded text. )
[comment]: <> ( @param	FileName		File name to save. Ex.: "Notes.txt", "Folder/SubFolder/MyTextFile.ini" )
[comment]: <> ( @param	BaseDirectory	Base directory to search for the file. )
[comment]: <> ( @return	True, if file loaded successfully. )
[comment]: <> ( bool LoadTextFile | FString& FileContent, const FString FileName, const EDirectory BaseDirectory = EDirectory::Custom )

:::api
### Load Text File

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Load a PNG image file into a Texture object. )
[comment]: <> ( @param	FileName		Image file name. Ex.: "Screenshot.png", "Folder/SubFolder/Screenshot.jpg" )
[comment]: <> ( @param	BaseDirectory	Base directory to search for the image file. )
[comment]: <> ( @return	Texture object. )
[comment]: <> ( UTexture2D* LoadImage | const FString FileName, const EDirectory BaseDirectory = EDirectory::Custom )

:::api
### Load Image

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Take a screenshot and save it as PNG, in engine's default screenshots folder. )
[comment]: <> ( @param	BaseDirectory	Base directory to save the screenshot. )
[comment]: <> ( @param	FileName		Screenshot file name. Ex.: "Screenshot.png", "Folder/SubFolder/Screenshot.jpg" )
[comment]: <> ( @param	bCaptureUI		Should Widgets be captured too. )
[comment]: <> ( void TakeScreenshot | const EDirectory BaseDirectory = EDirectory::ScreenShot, const FString FileName = "screenshot", const bool bCaptureUI = true )

:::api
### Take Screenshot

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Convert from Directory enum to String. )
[comment]: <> ( FString DirectoryToString | const EDirectory Directory )

:::api
### Directory to String

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( List all files in the given directory. )
[comment]: <> ( TArray<FString> ListFiles | FString Directory, const TArray<FString> FileExtensionFilter, const EDirectory BaseDirectory = EDirectory::Project, const bool bRecursively = false )

:::api
### List Files

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( List all subdirectories in the given directory. )
[comment]: <> ( TArray<FString> ListDirectories | FString Directory, const EDirectory BaseDirectory = EDirectory::Project, const bool bRecursively = false )

:::api
### List Directories

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Launch a file in the system's default application. )
[comment]: <> ( void LaunchFile | FString FilePath, const EDirectory BaseDirectory = EDirectory::Project )

:::api
### Launch File

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


---

## <span class="tag">Settings</span>


[//]: <> (=========================================================================================)

[comment]: <> ( Load a boolean setting from a '.ini' setting file. )
[comment]: <> ( bool GetBoolSetting | const ESettingsFile SettingFile, const FString Section, const FString Key, bool& SettingValue )

:::api
### Get Bool Setting

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Write a boolean setting value to existing a '.ini' setting file. )
[comment]: <> ( The results is stored at "<YourGameDir>\Saved\Config\Windows" )
[comment]: <> ( void SetBoolSetting | const ESettingsFile SettingFile, const FString Section, const FString Key, const bool Value, const FString CustomFile = "" )

:::api
### Set Bool Setting

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Load a string setting from a '.ini' setting file. )
[comment]: <> ( bool GetStringSetting | const ESettingsFile SettingFile, const FString Section, const FString Key, FString& SettingValue )

:::api
### Get String Setting

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Write a string setting value to existing a '.ini' setting file. )
[comment]: <> ( The results is stored at "<YourGameDir>\Saved\Config\Windows" )
[comment]: <> ( void SetStringSetting | const ESettingsFile SettingFile, const FString Section, const FString Key, const FString Value, const FString CustomFile = "" )

:::api
### Set String Setting

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Load a integer setting from a '.ini' setting file. )
[comment]: <> ( bool GetIntSetting | const ESettingsFile SettingFile, const FString Section, const FString Key, int32& SettingValue )

:::api
### Get Int Setting

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Write a integer setting value to existing a '.ini' setting file. )
[comment]: <> ( The results is stored at "<YourGameDir>\Saved\Config\Windows" )
[comment]: <> ( void SetIntSetting | const ESettingsFile SettingFile, const FString Section, const FString Key, const int32 Value, const FString CustomFile = "" )

:::api
### Set Int Setting

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Load a float setting from a '.ini' setting file. )
[comment]: <> ( bool GetFloatSetting | const ESettingsFile SettingFile, const FString Section, const FString Key, float& SettingValue )

:::api
### Get Float Setting

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Write a float setting value to existing a '.ini' setting file. )
[comment]: <> ( The results is stored at "<YourGameDir>\Saved\Config\Windows" )
[comment]: <> ( void SetFloatSetting | const ESettingsFile SettingFile, const FString Section, const FString Key, const float Value, const FString CustomFile = "" )

:::api
### Set Float Setting

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Convert from Setting File enum to object. )
[comment]: <> ( FString SettingFileToString | const ESettingsFile SettingFile )

:::api
### Setting File to String

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


---

## <span class="tag">UI</span>


[//]: <> (=========================================================================================)

[comment]: <> ( Remove the widget from memory. )
[comment]: <> ( void DestroyWidget | UWidget* Widget )

:::api
### Destroy Widget

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Encapsulates this Widget in a combination of Scale and Size boxes to keep this widget in a given aspect ratio, and add it to viewport. )
[comment]: <> ( void AddToConstraintViewport | UUserWidget* Widget, const int32 ZOrder = 0, const FVector2D Ratio = FVector2D | 1920, 1080 )

:::api
### Add to Constraint Viewport

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Take a picture of a widget and return it as a texture. )
[comment]: <> ( UTexture2D* CaptureWidget | UUserWidget* UserWidget, const FVector2D DrawSize = FVector2D | 512, 512 )

:::api
### Capture Widget

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Get all children, children of children and so on from the root widget. )
[comment]: <> ( TArray<UWidget*> GetNestedWidgets | UWidget* RootWidget )

:::api
### Get Nested Widgets

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Get all children, children of children and so on, of class, from the root widget. )
[comment]: <> ( TArray<UWidget*> GetNestedWidgetsOfClass | UWidget* RootWidget, const TArray<TSubclassOf<UWidget>> Classes )

:::api
### Get Nested Widgets Of Class

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Remove all Visible, HitTestInvisible or SelfHitTestInvisible widgets from the list. )
[comment]: <> ( TArray<UWidget*> RemoveVisibleWidgets | TArray<UWidget*> Widgets )

:::api
### Remove Visible Widgets

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Remove all Hidden or Collapsed widgets from the list. )
[comment]: <> ( TArray<UWidget*> RemoveHiddenWidgets | TArray<UWidget*> Widgets )

:::api
### Remove Hidden Widgets

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Return the given string in the 'On Printed Event' character-by-character in the given interval. )
[comment]: <> ( @param WorldContextObject )
[comment]: <> ( @param Text				Text to typewrite. )
[comment]: <> ( @param PrintedDelegate	Callback event to be called each time a character is printed. )
[comment]: <> ( @param CompletedDelegate Callback event to be called when the typewriting is completed. )
[comment]: <> ( @param Interval			Interval between each character print. )
[comment]: <> ( @param Sound				Sound to play when printing. )
[comment]: <> ( @param bOverlapSound		Play each key sound in an individual Audio Component or use the same Audio Component. )
[comment]: <> ( @param bSanitize			Remove trailing whitespaces. )
[comment]: <> ( @return Timer handle to control the effect. )
[comment]: <> ( ASmartTypewriter* PlayTypewriterEffect | UObject* WorldContextObject, const FText Text, )
[comment]: <> ( UPARAM | DisplayName = "On Printed Event" | const FTextPrintedDelegate& PrintedDelegate, )
[comment]: <> ( 		UPARAM | DisplayName = "On Completed Event" | const FTextCompletedDelegate& CompletedDelegate, )
[comment]: <> ( 		const float Interval = 0.02, USoundBase* Sound = nullptr, const bool bOverlapSound = false, const bool bSanitize = true )

:::api
### Play Typewriter Effect

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


---

## <span class="tag">Pipes</span>

[comment]: <> ( Replace in given string, occurrences of substrings with {var} format, for its value in a 'String Map' and 'String Tables'. )
[comment]: <> ( @param WorldContextObject )
[comment]: <> ( @param String		String to replace. )
[comment]: <> ( @param VariablesMap	Variables map to search in. )
[comment]: <> ( @param StringTables	String tables to search in. )
[comment]: <> ( @param Escape		Replace not found variables with this string. Leave empty to do not replace. )
[comment]: <> ( FString ReplaceVariables | const UObject* WorldContextObject, const FString String, const TMap<FName, FString> VariablesMap, const TArray<UStringTable*> StringTables, FString Escape = "" )

:::api
### Replace Variables

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Converts from float to signed number string. )
[comment]: <> ( N > 0 = +N; N == 0 = 0; N < 0 = -N; )
[comment]: <> ( static FText ToSignedNumber | const float Number )

:::api
### To Signed Number

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>



[//]: <> (=========================================================================================)

[comment]: <> ( Convert from pascal case to a user displayable text. )
[comment]: <> ( static FText ToDisplayText | const FString& String, const bool bIsBool = false )

:::api
### To Display Text

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Change first character from this string to upper case. )
[comment]: <> ( static FString UpperFirstLetter | const FString& String )

:::api
### Upper First Letter

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Change first character from this text to upper case. )
[comment]: <> ( FText TextUpperFirstLetter | const FText& Text )

:::api
### Text Upper First Letter

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Replace accentuated characters. )
[comment]: <> ( FString RemoveAccentuation | FString String )

:::api
### Remove Accentuation

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Remove rich text tags. )
[comment]: <> ( FString RemoveRichTextTags | FString String )

:::api
### Remove Rich Text Tags

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Convert the given string to a decimal hash with 10 numbers. )
[comment]: <> ( FString ToHash | const FString String )

:::api
### To Hash

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Convert from decimal to hexadecimal string. )
[comment]: <> ( FString ToHex | int64 Decimal )

:::api
### To Hex

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Encrypt the given string with AES. )
[comment]: <> ( static FString Encrypt | FString InputString, FString Key )

:::api
### Encrypt

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Decrypt the given string with AES. )
[comment]: <> ( FString Decrypt | FString InputString, FString Key )

:::api
### Decrypt

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Check if a string contains a :  | Colon. )
[comment]: <> ( static bool IsKeyValuePair | const FString& Pair )

:::api
### Is Key Value Pair

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Split a string into two parts, separated by :  | Colon. )
[comment]: <> ( Ex.: "Key:Value" -> "Key", "Value" )
[comment]: <> ( void ToKeyValuePair | const FString& Pair, FString& Key, FString& Value )

:::api
### To Key Value Pair

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Check if an array of strings contains a given key in the patter 'key:value'. )
[comment]: <> ( bool HasKeyValueTag | ToKeyValuePairt TArray<FString>& Tags, const FString& Key, FString& Value )

:::api
### Has Key Value Tag

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Create a new array equal to the given one, but with all repeated values removed. )
[comment]: <> ( template <cass T> )
[comment]: <> ( TArray<T> RemoveRepeatedValues | TArray<T> Array )

:::api
### Remove Repeated Values

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Overload functions to convert data types to string. )
[comment]: <> ( ! Will not compile if the type is a child class of it 'UObject' or custom class. )
[comment]: <> ( Similar to LexToString | Value, but with more types. )

[comment]: <> ( FORCEINLINE static FString ToString | const bool& Value )
[comment]: <> ( FORCEINLINE static FString ToString | const char* Value )
[comment]: <> ( FORCEINLINE static FString ToString | const FName& Value )
[comment]: <> ( FORCEINLINE static FString ToString | const FString& Value )
[comment]: <> ( FORCEINLINE static FString ToString | const FText& Value )
[comment]: <> ( FORCEINLINE static FString ToString | const uint8& Value )
[comment]: <> ( FORCEINLINE static FString ToString | const int32& Value )
[comment]: <> ( FORCEINLINE static FString ToString | const int64& Value )
[comment]: <> ( FORCEINLINE static FString ToString | const float& Value )
[comment]: <> ( FORCEINLINE static FString ToString | const double& Value )
[comment]: <> ( FORCEINLINE static FString ToString | const FVector& Value )
[comment]: <> ( FORCEINLINE static FString ToString | const FVector2D& Value )
[comment]: <> ( FORCEINLINE static FString ToString | const FRotator& Value )
[comment]: <> ( FORCEINLINE static FString ToString | const FTransform& Value )

[comment]: <> ( template<tyename T> )
[comment]: <> ( FString ToString | const TArray<T>& Array )

[comment]: <> ( template<tyename T> )
[comment]: <> ( FString ToString | const TSet<T>& Set )

[comment]: <> ( template<tyename K, typename V> )
[comment]: <> ( FString ToString | const TMap<K, V>& Map )

[comment]: <> ( template<tyename Type> )
[comment]: <> ( FString ToString | const Type& Enum )

:::api
### To String

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


---

## <span class="tag">Operators</span>

[comment]: <> ( Returns the first non-null operand in the given parameters list. )
[comment]: <> ( UObject* NullCoalescingOperator | UObject* A, UObject* B )

:::api
### Null Coalescing Operator

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Evaluate the given valid math expression. )
[comment]: <> ( double SolveMathExpression | const FString Expression )

:::api
### Solve Math Expression

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Check if two players are the same using their 'Unique Net ID'. )
[comment]: <> ( A 'Unique Net ID' is a system-designed identifier that uniquely represents a player's account across multiple sessions and devices. )
[comment]: <> ( In a multiplayer game, each player would be assigned a 'Unique Net ID'. )
[comment]: <> ( This ID remains consistent regardless of the device or platform the player is using. )
[comment]: <> ( Please note that the specific implementation of the Unique Net ID might vary depending on the online subsystem being used, like Steam, Xbox Live, PlayStation Network, or Epic Online Services, etc. )
[comment]: <> ( bool IsSameUniqueNetId | const FUniqueNetIdRepl& UniqueIdA, const FUniqueNetIdRepl& UniqueIdB )

:::api
### Is Same Unique Net Id

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>


[//]: <> (=========================================================================================)

[comment]: <> ( Check if the given player state belongs to the host or a client. )
[comment]: <> ( bool IsHost | const APlayerState* PlayerState )

:::api
### Is Host

!!!ghost
:construction: Under construction :construction:
Please refer to the in-engine documentation
!!!

:::
<br>

---
