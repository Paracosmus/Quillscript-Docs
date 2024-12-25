---
label: Visual Studio Code Extension
icon: plug
order: 1
---
# Visual Studio Code Extension

Quillscript script files are plain-text files, so you can write them using any text editor.

Specifically for Visual Studio Code, we provide a recommended extension for syntax highlighting and code completion and other valuable features for Quillscript writers and developers.

---

## Installation

1. In your internet browser, navigate to https://code.visualstudio.com/ and download Visual Studio Code for your platform.

2. Execute the downloaded file and follow the installation instructions.

3. With Visual Studio Code installed, execute the application, go to **Extensions**, and search and install the Quillscript extension.

![](../static/img/examples/vsc_installation.gif)

---

## Recommended Settings
We recommend some specific settings, completely optional, that can work and feel better with Quillscript files for most users.

Open your Visual Studio Code settings file, copy and paste the following settings, and save the file.

![](../static/img/examples/vsc_settings.gif)

### Editor Settings
```json #
// Quillscript.
"[quillscript]": {
    "editor.tabSize": 2,
    "editor.fontSize": 16,
    "editor.wordWrap": "off",
    "editor.renderWhitespace": "trailing",
    "editor.snippetSuggestions": "top",
    "editor.tabCompletion": "on",
    "files.insertFinalNewline": true,

    "editor.quickSuggestions": {
        "other": true,
        "comments": false,
        "strings": false
    },

    "editor.wordBasedSuggestions": "matchingDocuments",
}
```

### Syntax-Highlighting Settings
These settings paint your Quillscript code using the same color coding as the documentation, tutorials, and in-engine indicators.

```json #3,13,23,45,55,65,71,81,95,111,129,135,149,155,161,167,173,179
"editor.tokenColorCustomizations": {
    "textMateRules": [
        // Dialogue
        {
            "scope": [ "storage.type.class.qsc" ],
            "settings": { "foreground": "#0e4a8f", "fontStyle": "bold" }
        },
        {
            "scope": [ "entity.name.type.class.qsc" ],
            "settings": { "foreground": "#349df3", "fontStyle": "bold" }
        },

        // Option
        {
            "scope": [ "storage.type.enum.qsc" ],
            "settings": { "foreground": "#811818", "fontStyle": "bold" }
        },
        {
            "scope": [ "entity.name.type.enum.qsc" ],
            "settings": { "foreground": "#ef5350" }
        },

        // Label
        {
            "scope": [ "storage.type.namespace.qsc" ],
            "settings": { "foreground": "#ad1457", "fontStyle": "bold" }
        },
        {
            "scope": [ "entity.name.namespace.qsc" ],
            "settings": { "foreground": "#b64168", "fontStyle": "bold" }
        },
        {
            "scope": [ "variable.parameter.qsc" ],
            "settings": { "foreground": "#5f3542", "fontStyle": "bold" }
        },
        {
            "scope": [
                "punctuation.definition.parameters.begin.qsc",
                "punctuation.separator.comma.qsc",
                "punctuation.definition.parameters.end.qsc"
            ],
            "settings": { "foreground": "#4a4a4a" }
        },

        // Router
        {
            "scope": [ "keyword.control.loop.qsc" ],
            "settings": { "foreground": "#472399", "fontStyle": "bold" }
        },
        {
            "scope": [ "keyword.control.flow.qsc" ],
            "settings": { "foreground": "#854be9" }
        },

        // Command
        {
            "scope": [ "storage.type.function.qsc" ],
            "settings": { "foreground": "#2e7d32", "fontStyle": "bold" }
        },
        {
            "scope": [ "entity.name.function.qsc" ],
            "settings": { "foreground": "#60a863", "fontStyle": "bold" }
        },

        // Condition
        {
            "scope": [ "keyword.control.conditional.qsc" ],
            "settings": { "foreground": "#008f9c", "fontStyle": "bold" }
        },

        // Directive
        {
            "scope": [ "punctuation.definition.directive.qsc" ],
            "settings": { "foreground": "#fbc02d", "fontStyle": "bold" }
        },
        {
            "scope": [ "entity.name.other.preprocessor.macro.qsc" ],
            "settings": { "foreground": "#FFF176", "fontStyle": "bold" }
        },

        // Comment
        {
            "scope": [ "comment.title.qsc" ],
            "settings": { "foreground": "#e0e0e0", "fontStyle": "bold" }
        },
        {
            "scope": [ "comment.qsc" ],
            "settings": { "foreground": "#4A4A4A", "fontStyle": "italic" }
        },
        {
            "scope": [ "comment.topic.qsc" ],
            "settings": { "foreground": "#000000" }
        },

        // Instructions
        {
            "name": "String",
            "scope": [ "string.qsc" ],
            "settings": { "foreground": "#7e99a7" }
        },

        {
            "scope": [ "variable.other.constant.qsc" ],
            "settings": { "foreground": "#be5a09" }
        },
        {
            "scope": [ "variable.other.constant.text.qsc" ],
            "settings": { "foreground": "#fa9d52" }
        },

        // Operators
        {
            "scope": [ "keyword.operator.concat.qsc" ],
            "settings": { "foreground": "#303030", "fontStyle": "bold" }
        },
        {
            "scope": [
                "keyword.operator.qsc",
                "punctuation.accessor",
                "punctuation.terminator.qsc"
            ],
            "settings": { "foreground": "#BBBBBB" }
        },
        {
            "scope": [ "meta.brace.round.qsc" ],
            "settings": { "foreground": "#4a4a4a" }
        },

        // Number
        {
            "scope": [ "constant.number.qsc" ],
            "settings": { "foreground": "#008f9c" }
        },

        // Richtext
        {
            "scope": [ "entity.name.tag.qsc" ],
            "settings": { "foreground": "#226fff" }
        },
        {
            "scope": [ "entity.other.attribute-name.qsc" ],
            "settings": { "foreground": "#99defd" }
        },
        {
            "scope": [ "punctuation.separator.key-value.qsc" ],
            "settings": { "foreground": "#99defd" }
        },

        // Variable
        {
            "scope": [ "variable.qsc" ],
            "settings": { "foreground": "#99defd" }
        },

        // Definition
        {
            "scope": [ "variable.other.global.qsc" ],
            "settings": { "foreground": "#FFF59D" }
        },

        // Delay
        {
            "scope": [ "variable.delay.qsc" ],
            "settings": { "foreground": "#455A64" }
        },

        // Parameter
        {
            "scope": [ "parameter.qsc" ],
            "settings": { "foreground": "#475f3c", "fontStyle": "italic" }
        },

        // Keyword
        {
            "scope": [ "constant.language.qsc" ],
            "settings": { "foreground": "#0059ff" }
        },

        // Enumerator
        {
            "scope": [ "variable.other.enummember.qsc" ],
            "settings": { "foreground": "#238dec" }
        }
    ]
}
```

---

## View Project
You can open your Unreal Engine project root folder directly in Visual Studio Code to have a broad view of your project files and manage all your Quillscript source files.

![](../static/img/examples/vsc_view.gif)

---