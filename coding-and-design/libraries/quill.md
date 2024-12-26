---
label: Quill
icon: paintbrush
order: 2
---
# Quill
> Quillscript Function Library

The **Quillscript Function Library** is a dedicated collection of utility functions designed to enhance the functionality and ease of use of the Quillscript Plugin in Unreal Engine.

This library offers a set of specialized tools and features for Quillscript Plugin users, enabling efficient coding, automation, and customization within your Quillscript-powered projects.

---

## Variables

:::api
### <span class="comment">Register Variable Modifier</span>

Register a variable modifier.

When a Quillscript variable value is requested, the delegate event is played before retrieving the value, allowing the code to modify the variable value beforehand or to play some required code.

```rust
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

:::api
### <span class="comment">Unregister Variable Modifier</span>

Unregister a variable modifier.

```rust
VariableName: name
```

==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/_fkpkbmi/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp
#include "Utils/Quill.h"
...

UQuill::UnregisterVariableModifier(this, "VariableName");
```
===

:::

---
