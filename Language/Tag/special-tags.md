---
label: Special Tags
icon: tag
---
# Special Tags

Special tags are tags with built-in behavior. They are used to decorate statements to obtain specific plugin behaviors.

---

## Once
This Special Tag can be used if you want a statement to play only once, doesn't matter how many times the script flow passes through that point.

```q #
- Shopkeeper | #once
  Greetings traveler!
  Welcome to the shop of the great wizard, Zeddicus.

- Shopkeeper
  How may the great Zeddicus be of service to you today?

$ ShowShopInventory

```

!!!warning
**Keep Visited Statements** must be enabled in [Quillscript Settings](../../coding-and-design/settings/) for this tag to work
!!!

---

## Mark
The #mark tag is used to tell the Interpreter to store a counter of how many times this statement played when the Keep Visited Statements setting is turned off.

```q
$ a = 10 | #mark
```

---
