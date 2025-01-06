---
label: Smart Typewriter
icon: note
order: 2
---
# Smart Typewriter

The Smart Typewriter is a reusable object class that can be used to create a typewriter effect in your game. It can be used to display text in a cinematic way, with a typing sound and a delay between each character.

The built-in dialogue box uses the Smart Typewriter to display text. The Smart Typewriter can be customized to fit your game's style and needs.

---

## <span class="comment">Reusable Function</span>

You can apply the Smart Typewriter to any text widget in Unreal Engine using the [Play Typewriter Effect](../libraries/tools.md#play-typewriter-effect) utility function.

[!embed](https://blueprintue.com/render/devhhybq/)

---

## <span class="comment">Timer delays</span>

The Smart Typewriter accepts custom pauses while printing a text line. You can set a numeric delay inside double parenthesis `((delay))`.

```q
- Leonidas
  This...((0.1)) is...((0.1)) Sparta!
```

By default the typewriter will interpret the delay as seconds. You can change the unit by adding it after the number:

```q
- Bob
  Wow!((100ms)) I can't believe you are here, err...((1s)) Alice.
```

The supported units are:

| {.compact}
--- | ---
`ms`  | milliseconds
`cs`  | centiseconds
`ds`  | deciseconds
`s`   | seconds
`min` | minutes
`h`   | hours

---

## <span class="comment">Substring delays</span>

The Smart Typewriter can also pause between substrings. You can set a delay after a substring using a map.

==- [!badge variant="primary" size="l" icon="file-binary" corners="Square" text="Blueprint"]

[!embed](https://blueprintue.com/render/mgqjtmba/)

==- [!badge variant="warning" size="l" icon="file-code" corners="Square" text="C++"]
```cpp #3-6 Add Substring Delays
TObjectPtr<ASmartTypewriter> Typewriter = ...

Typewriter->AddSubstringsDelays({
    { "...", 2 },
    { ".",   1 }
});
```
===

---
