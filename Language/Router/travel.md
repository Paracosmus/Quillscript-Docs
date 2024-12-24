---
label: Travel
icon: milestone
order: 1
---
# Travel

Travel is actually a [built-in function](../Command/built-in-functions.md) disguised as a Router statement. It works as other routers, navigating from that point to a given target, but differently from a Router statement, the Travel built-in function allows you to target another script.

The target Script is referenced using its **id** or **Script Reference by Path**.

```q
$ Travel @MyOtherScript                        // By id
$ Travel {&/Game/MyOtherScript.MyOtherScript}  // By Script Reference
```

You can also route directly to a label inside the target Script.

```q
$ Travel @MyOtherScript LabelName                        // By id
$ Travel {&/Game/MyOtherScript.MyOtherScript} LabelName  // By Script Reference
```

!!!warning
Be aware that the Travel built-in function will immediately terminate the current script playing and start the target Script in a new Interpreter instance.
!!!

---

## Travel Pass
It's often required to keep the current script and interpreter settings while traveling from one script to another. The **$ Travel** built-in function will start the new script in a clean instance.

If you need to keep the current settings, use the **\$ TravelPass** instead. It works the same as **\$ Travel**, but it makes a copy of the current Interpreter and keeps Interpreter and Script settings.

---
