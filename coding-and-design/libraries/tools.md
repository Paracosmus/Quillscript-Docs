---
label: Tools
icon: tools
order: 1
---
# Tools
> Tools Function Library

The **Tools Function Library** is a versatile collection of extra utility functions designed to streamline and simplify common tasks in Unreal Engine game development.

This library is a useful resource for any Unreal Engine project, offering a wide range of functions that provide essential functionality for various game development needs.

---

## Print

:::api
### <span class="comment">Print</span>

Print a message on screen and/or console. (In Development, Debug or Editor mode)

Check your Verbosity setting to select where this message is printed.

```rust #1-3
Parameters
Copy
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
PRINT("Print this message");

// Function call.
UTools::Print("Print this message", MyObject);
```
===

:::

---
