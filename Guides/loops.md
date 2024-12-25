---
label: Loops
icon: iterations
order: 2
---
# Loops
[Labels](../Language/Label/) and [Routers](../Language/Router/) can be used to create common code loops like a while, for and for each loop.

Below we list a few examples to base your own script code and story loops.

---

## For
The following loop runs 10 times before continuing the story flow.

```q #1,2,7,8
$ :i = 0
@ MyForLoop | ? {:i} < 10

  - .
    Index: {:i}

$ :i += 1
-> MyForLoop

```

---

## While
The following loop runs until the custom function <span class="command">$ MyEscapeFunction</span> changes the value of the temporary variable <span class="command">:flag</span> to <span class="keyword">on</span>.

```q #1,2,7,8
$ :flag = off
@ MyWhileLoop | ? {:flag} == off

  // This function changes the value of the 'flag' quillscript variable.
  $ MyEscapeFunction

$ Wait 0.1    // Prevent an infinity loop from locking the frame
-> MyWhileLoop

```

---

## For Each
The following loop shows the value of all elements in an array.

### Array or Set

```q #4,5,10,11
$ &Level.ArrayVar		             // Custom function: Store the Array in a variable called '$Array'
$ ^Quillscript.Tools.Length {$Array} // Custom function: Store the length in a variable called '$ReturnValue'

$ :i = 0
@ MyArrayForEachLoop | ? {:i} < {$ReturnValue}

  - .
    Array Value: <b>{$Array::{:i}}</>

$ :i += 1
-> MyArrayForEachLoop

```

### Map
The following loop shows the key-value pair of all elements in a map.

```q #5,6,11,12
$ MyMapVar			               // Custom function: Store the Map in a variable called '$Map'
$ MyMapKeys		                   // Custom function: Store the Map keys in a variable called '$Keys'
$ ^Quillscript.Tools.Length {$Map} // Store the length in a variable called '$ReturnValue'

$ :i = 0
@ MyMapForEachLoop | ? {:i} < {$ReturnValue}

  - .
    Map Key-Value Pair: <b>{$Keys::{:i}} = {$Map::{$Keys::{:i}}}</>

$ :i += 1
-> MyMapForEachLoop

```

---
