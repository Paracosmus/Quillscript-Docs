---
label: Editor Tools
icon: paste
order: 1
---
# Editor Tools
> Editor Tools Function Library

A collection of functions that can be used to perform various task in the [Editor](https://dev.epicgames.com/documentation/unreal-engine/tools-and-editors-in-unreal-engine) and [Editor Utility](https://dev.epicgames.com/documentation/unreal-engine/scripting-the-unreal-editor-using-blueprints) functions.

---

## <span class="directive">Widgets</span>

[//]: <> (=========================================================================================)

:::api
### Spawn Tab

Spawn an Editor tab with the given **Editor Utility Widget**.

```rust !#1-2 Parameters
TabTitle: Text
WidgetPath: string
(C++ Only) TabIcon: FSlateIcon
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
$ ^QuillscriptEditor.EditorTools.SpawnTab 'Tab Title' /Game/Path/To/MyWidget.MyWidget

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/nldu0mg1/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/EditorTools.h"
...

UEditorTools::SpawnTab(
    TXT("Tab Title"),
    "/Game/Path/To/MyWidget.MyWidget",
    FSlateIcon(InStyleSetName, "LevelEditor.Tabs.Details")
);
```
===

:::
<br>

---

## <span class="directive">Files</span>

[//]: <> (=========================================================================================)

:::api
### Prompt Save to Text File

Prompt developer to save content to a text file.

```rust !#1-4 Parameters
FileContent: string
FileName: string = "filename",
BaseDirectory: EDirectory = Custom [Custom, Project, ProjectContent, ProjectSaved, ProjectConfig, ScreenShot, Launch]
FileType: string = "Text File|*.txt"
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
$ ^QuillscriptEditor.EditorTools.PromptSaveToTextFile 'File Content' 'filename' Custom 'Text File\|*.txt'

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/h82u7gzi/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/EditorTools.h"
...

UEditorTools::PromptSaveToTextFile(
    'File Content',
    'filename',
    EDirectory::Custom,
    'Text File|*.txt'
);
```
===

:::
<br>

[//]: <> (=========================================================================================)

:::api
### Prompt Load Text File

Prompt developer to load content from text file(s).

```rust !#1-5 Parameters
FilesContents: array[string]
SubFolderPath: string = "",
BaseDirectory: EDirectory = Custom [Custom, Project, ProjectContent, ProjectSaved, ProjectConfig, ScreenShot, Launch]
FileType: string = "Text Files|*.txt"
FileDialogFlags: EFileSelection = Single [Single, Multiple]
```

==- [!badge variant="success" size="l" icon="file-symlink-file" corners="Square" text="Quillscript"]
```q
$ ^QuillscriptEditor.EditorTools.PromptLoadTextFile 'Sub/Folder/Path' Custom 'Text Files\|*.txt' Single

```
==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/8dtsi92n/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/EditorTools.h"
...

UEditorTools::PromptLoadTextFile(
    'Files Contents',
    'Sub/Folder/Path',
    EDirectory::Custom,
    'Text Files|*.txt',
    EFileSelection::Single
);
```
===

:::
<br>

---
