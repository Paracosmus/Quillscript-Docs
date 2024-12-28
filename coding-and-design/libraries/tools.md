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

:::api
### Log

Print a message on screen and/or console with control params. (In Development, Debug or Editor mode)

Check your [Verbosity setting](../settings/settings-details.md#verbosity) to select where this message is printed.

```rust !#1 Parameters
Message: string
(Omittable) Owner: ref              // Object that called this function.
(Omittable) PrintType: PrintType    [ Log, Success, Warning, Error ]
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
$ ^Quillscript.Tools.Log Hello
$ ^Quillscript.Tools.Log 'Print this message'
$ ^Quillscript.Tools.Log 'Print this message' {&Script} Error

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/02vrlz41/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Tools.h"
...

UTools::Log("Print this message", MyObject, EPrintType::Error);
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Print

Print a message on screen and/or console. (In Development, Debug or Editor mode)

Check your [Verbosity setting](../settings/settings-details.md#verbosity) to select where this message is printed.

```rust !#1 Parameters
Message: string
(Omittable) Owner: ref    // Object that called this function.
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

:::api
### Success

Print a success message on screen and/or console. (In Development, Debug or Editor mode)

Check your [Verbosity setting](../settings/settings-details.md#verbosity) to select where this message is printed.

```rust !#1 Parameters
Message: string
(Omittable) Owner: ref    // Object that called this function.
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
$ ^Quillscript.Tools.Success Hello
$ ^Quillscript.Tools.Success 'Print this message'
$ ^Quillscript.Tools.Success 'Print this message' {&Script}

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/r774746_/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Tools.h"
...

// Macro (Only inside an UObject method)
SUCCESS("Print this message");

// Function call.
UTools::Success("Print this message", MyObject);
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Warning

Print a warning message on screen and/or console. (In Development, Debug or Editor mode)

Check your [Verbosity setting](../settings/settings-details.md#verbosity) to select where this message is printed.

```rust !#1 Parameters
Message: string
(Omittable) Owner: ref    // Object that called this function.
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
$ ^Quillscript.Tools.Warning Hello
$ ^Quillscript.Tools.Warning 'Print this message'
$ ^Quillscript.Tools.Warning 'Print this message' {&Script}

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/a_n_egnm/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Tools.h"
...

// Macro (Only inside an UObject method)
WARNING("Print this message");

// Function call.
UTools::Warning("Print this message", MyObject);
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Error

Print an error message on screen and/or console. (In Development, Debug or Editor mode)

Check your [Verbosity setting](../settings/settings-details.md#verbosity) to select where this message is printed.

```rust !#1 Parameters
Message: string
(Omittable) Owner: ref    // Object that called this function.
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
$ ^Quillscript.Tools.Error Hello
$ ^Quillscript.Tools.Error 'Print this message'
$ ^Quillscript.Tools.Error 'Print this message' {&Script}

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/zu0udd5r/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Tools.h"
...

// Macro (Only inside an UObject method)
ERROR("Print this message");

// Function call.
UTools::Error("Print this message", MyObject);
```
===
:::
<br>


---

## <span class="tag">Utilities</span>


[//]: <> (=========================================================================================)

:::api
### Rename Object

Rename the given object.

This function is useful to give a know name to an object and reference it later by name in script like:
`$ &ObjName.ObjFunction`

```rust !#1-2 Parameters
Object: ref
NewName: string
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
$ ^Quillscript.Tools.RenameObject {&RefName} NewRefName
$ &NewRefName.MyFunction

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/5rav4ast/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Tools.h"
...

UTools::RenameObject(MyObject, "RefName");
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Find Class by Path

Attempts to locate a class by its path, specified as a string. This function is a valuable utility for dynamically finding and accessing classes within your Unreal Engine project based on their defined paths.

```rust !#1 Parameters
Path: string
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
// Store class reference in {&ReturnValue}.
$ ^Quillscript.Tools.FindClassByPath /Game/Path/To/Blueprint.Blueprint
$ ^Quillscript.Tools.FindClassByPath /Game/Path/To/Blueprint.Blueprint_C
$ ^Quillscript.Tools.FindClassByPath Module.ClassName

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/ycrh00ia/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Tools.h"
...

// Blueprint class.
TObjectPtr<UClass> BlueprintPath{ UTools::FindClassByPath("/Game/Path/To/My/Blueprint.Blueprint") };
TObjectPtr<UClass> ClassPath{ UTools::FindClassByPath("/Game/Path/To/My/Blueprint.Blueprint_C") };

// C++ class.
TObjectPtr<UClass> CppClass{ UTools::FindClassByPath("Module.ClassName") };
TObjectPtr<UClass> CppClassExample{ UTools::FindClassByPath("Engine.Actor") };
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Get Class Default Object

Get the default object from the given class. This function is useful to expose the Default Object to Blueprints.

```rust !#1 Parameters
Class: ref[Class]
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
// Store class reference in {&ReturnValue}.
$ ^Quillscript.Tools.GetClassDefaultObject {&Class}

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/nmoejq13/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Tools.h"
...

TObjectPtr<UClass> DefaultObject{ UTools::GetClassDefaultObject(Class) };
```
===
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

:::api
### Call Function by Name

Call a Target's function by name and return its Return Value and Outer Parameters.

This is a simplified general usage version of _Interpreter.CallFunctionOnTarget()_ that do not create Quillscript variables and script references.

```rust !#1-4 Parameters
WorldContextObject: ref
Target: ref
FunctionName: name
Parameters: array[string]
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
// Store class reference in {&ReturnValue}.
$ ^Quillscript.Tools.CallFunctionByName {&Target} MyFunction '("10","true")'

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/enu_tzm2/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Tools.h"
...

TMap<FName, FString> OuterParams{
    UTools::CallFunctionByName(
        WorldContextObject,
        Target,
        "MyFunction",
        TArray<FString>({"10", "true"})
    )
};
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Has Authority

Serves as a shortcut utility designed for use inside static methods that have a **WorldContextObject** parameter. It allows you to determine whether the current execution context possesses authority, using the **GetFirstPlayerController**, which is often associated with server or authoritative roles in networked multiplayer games.

While this function provides a convenient way to check authority within static methods, it's important to note that if your function already has access to **HasAuthority()** through other means, it's advisable to use those methods instead.

```rust !#1 Parameters
WorldContextObject: ref
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
// Store result in {&ReturnValue}.
$ ^Quillscript.Tools.HasAuthority

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/l0mx63ik/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Tools.h"
...

// Macro (Only inside functions with a 'WorldContextObject' variable)
if (HAS_AUTHORITY())
{
    // Implementation.
}

// Function call.
if (UTools::HasAuthority(WorldContextObject))
{
    // Implementation.
}
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Is Module Loaded

Check whether a specific module or plugin is currently loaded within the Unreal Engine project. This function provides a straightforward way to determine if a particular module or plugin is available and active for use in your project.

```rust !#1 Parameters
ModuleName: name
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
// Store result in {&ReturnValue}.
$ ^Quillscript.Tools.IsModuleLoaded ModuleName

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/ok4lwslr/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Tools.h"
...

if (UTools::IsModuleLoaded(ModuleName))
{
    // Implementation.
}
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Generate Random String

Check whether a specific module or plugin is currently loaded within the Unreal Engine project. This function provides a straightforward way to determine if a particular module or plugin is available and active for use in your project.

```rust !# Parameters
(Omittable) Size: byte = 8
(Omittable) Letters: bool = true
(Omittable) Numbers: bool = true
(Omittable) Symbols: bool = false
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
// Store result in {&ReturnValue}.
$ ^Quillscript.Tools.GenerateRandomString
$ ^Quillscript.Tools.GenerateRandomString 8 true true true

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/z_h5ovvb/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Tools.h"
...

FString RandomString{ UTools::GenerateRandomString() };
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Retrieve Option

Fetch a level transition option by providing the option's key. This function is particularly useful when you need to access specific transition options after a level change, allowing you to retrieve and utilize option values as needed.

```rust !#1-3 Parameters
WorldContextObject: ref
Key: string
Value: string
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
// Store if level option exists in {$ReturnValue}.
// Store level option value in {&Value}.
$ ^Quillscript.Tools.RetrieveOption MyKey

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/e2i7s1s9/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Tools.h"
...

FString Key, Value;
FString RandomString{ UTools::RetrieveOption(WorldContextObject, Key, Value) };
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Sort Strings Alphabetically

Sort an array of strings in alphabetical order. This function allows you to arrange a collection of strings into ascending alphabetical sequence, making it easier to manage and organize string data.

```rust !#1 Parameters
Strings: array[string]
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
// Store result in {&ReturnValue}.
$ MyArray = '("Snowfall","Unreal Engine","Quillscript")'
$ ^Quillscript.Tools.SortStringsAlphabetically {MyArray}

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/noqcdf4a/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Tools.h"
...

TArray<FString> SortedArray{ UTools::SortStringsAlphabetically(StringsArray) };
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Register String Table

Register a string table by path. This function is useful when a string table is used by path and never referenced, causing it to not be loaded during runtime.

```rust !#1 Parameters
StringTablepPath: name
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
// Store result in {&ReturnValue}.
$ ^Quillscript.Tools.RegisterStringTable /Game/Folder/MyTable.MyTable

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/aqe91sbo/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Tools.h"
...

UTools::RegisterStringTable("/Game/Folder/MyTable.MyTable");
```
===
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

:::api
### Get Project Name

Retrieves the project name that is configured in the `Edit > Project Settings > Project > Description > Project Name` field. This function allows you to access the project's name programmatically.

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
// Store result in {&ReturnValue}.
$ ^Quillscript.Tools.GetProjectName

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/ijyuc495/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Tools.h"
...

FString ProjectName{ UTools::GetProjectName() };
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Get Project Version

Retrieves the project version that is set in the `Edit > Project Settings > Project > Description > Project Version` field. You can use this function to access the project's version number within your code.

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
// Store result in {&ReturnValue}.
$ ^Quillscript.Tools.GetProjectVersion

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/b4o5zq1w/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Tools.h"
...

FString ProjectVersion{ UTools::GetProjectVersion() };
```
===
:::
<br>


[//]: <> (=========================================================================================)

:::api
### Get Company Name

Fetches the company name specified in the `Edit > Project Settings > Project > Description > Company Name` field. This function is useful for obtaining the company name associated with your project.

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
// Store result in {&ReturnValue}.
$ ^Quillscript.Tools.GetCompanyName

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/24z61e34/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Tools.h"
...

FString CompanyName{ UTools::GetCompanyName() };
```
===
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
