---
label: Built-in Functions
icon: file-symlink-file
order: 1
---
# Built-In Functions

List all built-in functions available in script

## Flow

==- <span class="command">Restart</span>
Go back to the beginning of the script.

```q Example
$ Restart

```
===

==- <span class="command">Next</span>
Go to next Statement.

```q Example
$ Next

```
===

==- <span class="command">Rollback</span>
Go to previous executed Statement.

```q Example
$ Rollback

```
===

==- <span class="command">Repeat</span>
Restart current label statement.

```q Example
$ Repeat

```
===

==- <span class="command">Done</span>
Advance to next label statement.

```q Example
$ Done

```
===

==- <span class="command">Return</span>
Go back to last executed Router statement.

```q Example
$ Return

```
===

==- <span class="command">End</span>
End this script.

```q Example
$ End

```
===

==- <span class="command">Kill</span>
Same as <span class="command">$ End</span>, but does not apply Script Settings After.

```q Example
$ Kill

```
===

==- <span class="command">Restore</span>
Allows this scene to proceed.

```q Example
$ Restore

```
===

==- <span class="command">Stop</span>
Prevents this scene from proceeding.

```q Example
$ Stop

```
===

==- <span class="command">Sleep</span>
Stops the script play, remove the script widgets from the screen, and apply _Script Settings After_.

This function is intended to stop a script play and restore the game to its default state until the scene is restored with the command <span class="command">$ Wakeup</span>.

```q Example
$ Sleep

```
===

==- <span class="command">Wakeup</span>
Restore and continue a script play from a sleep state caused by the <span class="command">$ Sleep</span> command.

```q Example
$ Wakeup

```
===

==- <span class="command">Wait</span>
Stop script for a few seconds.

```rust Parameters
Duration: float
```

```q Example
$ Wait 3
$ Wait 0.25

```
===

==- <span class="command">Timer</span>
Execute the given command after the given time.

```rust Parameters
Duration: float
Command: string
(Omittable) Async: bool
```

```q Example
$ Timer 5 "^Quillscript.Tools.Print '5 seconds passed'"
$ Timer 1.5 "&GameInstance.MyFunction 36" true

```
===

==- <span class="command">Travel</span>
End current Script and play a new script from start or from label.

```rust Parameters
TargetScript: string | ref
(Omittable) StartingLabel: string
```

```q Example by Id
$ Travel @Intro            // Travel and play from start
$ Travel @Act1 Chapter2    // Travel and play from label 'Chapter2'

```

```q Example by Script Reference
$ Travel {&/Game/Scripts/Intro.Intro}                // Travel and play from start
$ Travel {&/Plugin/Screenplay/Act1.Act1} Chapter2    // Travel and play from label 'Chapter2'

```
===

==- <span class="command">Travel Pass</span>
End current Script and play a new script from start or from label.

It is the same as <span class="command">$ Travel</span>, but instead of a new clean Interpreter, it makes a of the current Interpreter, keeping settings and changes. Also, it uses the same _Script settings_ as the current Script object and passes them to the given script.

```rust Parameters
TargetScript: string | ref
(Omittable) StartingLabel: string
```

```q Example by Id
$ TravelPass @Intro            // Travel pass and play from start
$ TravelPass @Act1 Chapter2    // Travel pass and play from label 'Chapter2'

```

```q Example by Script Reference
$ TravelPass {&/Game/Scripts/Intro.Intro}                // Travel pass and play from start
$ TravelPass {&/Plugin/Screenplay/Act1.Act1} Chapter2    // Travel pass and play from label 'Chapter2'

```
===

---

## State

==- <span class="command">Print</span>
Debugger function to print the given Quillscript variable's value.

```rust Parameters
VariableName: string
```

```q Example
$ Print myVariable

```
===

==- <span class="command">Delete</span>
Delete the given Quillscript variable.

```rust Parameters
VariableName: string
```

```q Example
$ Delete myVariable

```
===

==- <span class="command">Notify</span>
Notify all registered observers in 'UQuillscriptSubsystem::OnNotified(FString)'.

```rust Parameters
Message: string
```

```q Example
$ Notify 72
$ Notify 'Boss defeated'

```
===

---

## Input

==- <span class="command">Set Input Mode</span>
Change the game input mode.

```rust Parameters
InputMode: InputMode                        [ GameOnly, GameAndUI, UIOnly ]
(Omittable) MouseLockMode: MouseLockMode    [ DoNotLock, LockOnCapture, LockAlways, LockInFullscreen ]
(Omittable) HideCursorDuringCapture: bool
(Omittable) WidgetToFocus: ref
```

```q Example
$ SetInputMode GameOnly
$ SetInputMode GameAndUI LockAlways
$ SetInputMode UIOnly LockOnCapture true {&MyWidget}

```
===

==- <span class="command">Input Enable</span>
Enable input, move input, and look input.

```q Example
$ InputEnable

```
===

==- <span class="command">Input Disable</span>
Disable input, move input, and look input.

```q Example
$ InputDisable

```
===

==- <span class="command">Input Mode</span>
Show mouse cursor.

```q Example
$ ShowMouseCursor

```
===

==- <span class="command">Hide Mouse Cursor</span>
Hide mouse cursor.

```q Example
$ HideMouseCursor

```
===

---

## User Interface

==- <span class="command">Use</span>
Use the specified class or keyword for Dialog Box, Selection Box and Background Box and Sprite Box.

**By Keywords:**

* **Default:** Reset all boxes classes to default.
* **DialogBox:** Reset the Dialog Box class to default.
* **SelectionBox:** Reset the Selection Box class to default.
* **BackgroundBox:** Reset the Background Box class to default.
* **SpriteBox:** Reset the Sprite Box class to default.

**By Class Path:**

* **C++ Class:** /Script/Module.DialogBoxClass
* **Blueprint Class:** /Game/Path/To/Folder/MyDialogBox.MyDialogBox

```rust Parameters
WidgetClassPath: string
```

```q Example
$ Use Default
$ Use DialogBox
$ Use /Script/Quillscript.DialogBox
$ Use /Game/MyFolder/MyDialogBox.MyDialogBox

```
===

==- <span class="command">Show Dialog Box</span>
Add Dialog Box to viewport.

```q Example
$ ShowDialogBox

```
===

==- <span class="command">Show Selection Box</span>
Add Selection Box to viewport.

```q Example
$ ShowSelectionBox

```
===

==- <span class="command">Show Background Box</span>
Add Background Box to viewport.

```q Example
$ ShowBackgroundBox

```
===

==- <span class="command">Remove Dialog Box</span>
Remove Dialog Box from viewport.

```q Example
$ RemoveDialogBox

```
===

==- <span class="command">Remove Selection Box</span>
Remove Selection Box from viewport.

```q Example
$ RemoveSelectionBox

```
===

==- <span class="command">Remove Background Box</span>
Remove Background Box from viewport.

```q Example
$ RemoveBackgroundBox

```
===

==- <span class="command">Show</span>
Show Dialog Box and Selection Box.

```q Example
$ Show

```
===

==- <span class="command">Hide</span>
Hide Dialog Box and Selection Box.

```q Example
$ Hide

```
===

==- <span class="command">Background</span>
Change the background image on screen with a transition animation.

```rust Parameters
Image: ref
(Omittable) Transition: string [ none, fade, dissolve, scrollup, shake ]
(Omittable) Duration: float
```

```q Example
$ Background {&/Game/Scenarios/School.School}
$ Background {&MyRef} dissolve 1

```
===

==- <span class="command">Bg</span>
An alias function for <span class="command">$ Background</span>.

```rust Parameters
Image: ref
(Omittable) Transition: string [ none, fade, dissolve, scrollup, shake ]
(Omittable) Duration: float
```

```q Example
$ Bg {&/Game/Scenarios/School.School}
$ Bg {&MyRef} dissolve 1

```
===

==- <span class="command">Sprite</span>
Create a User Interface object to display an image on screen from the default **SpriteBox** class and set a Script Reference for the created object.

It is most useful to display, animate and handle character images and illustrations during dialogues.

```rust Parameters
Name: name
(Omittable) Class: class
```

```q Example
$ Sprite Alice

// Or define another class instead of the default one.
// $ Sprite Alice {&/Game/Path/To/SpriteBoxClass.SpriteBoxClass_C}

// left, center, right for slots; 0.5:0.5 for screen percentage; 100,100 for pixels;
$ &Alice.Position  left

// Animation name, start at time, num loops, play mode, playback speed, destroy on end.
$ &Alice.Animate   fade 0 1 Forward 1 false

$ &Alice.Layer     10
$ &Alice.Rotate    180
$ &Alice.Scale     2 2

// Script path reference to an asset.
$ &Alice.Show 	   {&/Game/Assets/Alice_Happy.Alice_Happy}

```

===

---

## Media

==- <span class="command">Play Sound</span>
Play a sound asset.

```rust Parameters
Sound: ref
(Omittable) Channel: string
(Omittable) Volume: float
(Omittable) FadeDuration: float
```

```q Example
$ PlaySound {&/Game/Voices/Line33.Line33}
$ PlaySound {&/Game/SFXs/Explosion.Explosion} SFX 2
$ PlaySound {&/Game/Musics/Piano.Piano} BackgroundMusic 0.5 0.5

```
===

==- <span class="command">Voice</span>
Play a sound asset.

Same as: `PlaySound {&/Path} 'voice' volume 0`

```rust Parameters
Sound: ref
(Omittable) Volume: float
```

```q Example
$ Voice {&/Game/Voices/Line33.Line33}
$ Voice {&/Game/Character/Greetings.Greetings} 1

```
===

==- <span class="command">Music</span>
Play a sound asset.

Same as: `PlaySound {&/Path} 'music' volume 0`

```rust Parameters
Sound: ref
(Omittable) Volume: float
(Omittable) FadeDuration: float
```

```q Example
$ Music {&/Game/Musics/Piano.Piano}
$ Music {&/Game/Environment/Wind.Wind} 0.75
$ Music {&/Game/Environment/Birds.Birds} 0.5 1

```
===

==- <span class="command">SFX</span>
Play a sound asset.

Same as: `PlaySound {&/Path} 'sfx' volume 0`

```rust Parameters
Sound: ref
(Omittable) Volume: float
```

```q Example
$ SFX {&/Game/Car/Engine.Engine}
$ SFX {&/Game/SFXs/Explosion.Explosion} 2

```
===

==- <span class="command">Stop Sound</span>
Stop the sound asset playing.

```rust Parameters
(Omittable) Channel: string
(Omittable) FadeDuration: float
```

```q Example
$ StopSound voice
$ StopSound music 0.5

```
===

==- <span class="command">Stop All Sounds</span>
Stop all sound assets from all channels.

```rust Parameters
(Omittable) FadeDuration: float
```

```q Example
$ StopAllSounds
$ StopAllSounds 0.5

```
===

==- <span class="command">Play Animation</span>
Play animation on target skeletal mesh.

```rust Parameters
SkeletalMeshComponent: ref
AnimationReference: ref
(Omittable) Loop: bool
```

```q Example
$ PlayAnimation {&Mesh} {&/Game/Animations/Idle.Idle}
$ PlayAnimation {&Mesh} {&/Game/Animations/Running.Running} true

```
===

---

## Helper

==- <span class="command">Roll</span>
Roll a number of dice. Select a random number in range.
The result is stored in a Quillscript variable named `{$ReturnValue}`.

```rust Parameters
DieSides: integer
Quantity: integer
```

```q Example
$ Roll 2     // heads or tails
$ Roll 6     // d6
$ Roll 20    // d20
$ Roll 100
$ Roll 17 2
$ Roll 12 10

if: {$ReturnValue} > 10
    $ ^Quillscript.Tools.Success 'You win!'

```
===

---
