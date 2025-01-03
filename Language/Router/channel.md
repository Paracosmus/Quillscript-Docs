---
label: Channel
icon: arrow-both
order: 2
---
# Channel

A Channel memorises the point where a Router was played, and return to that point when the target label finishes to play.

- A Channel statement starts with a **<-> (_Less Than, Dash and Greater Than_)**, immediately followed by a space.

```q #12,20
<@> Answer

  - George
    Here is my license.


@ Start

  - Officer
    Oi, do you have a license for that?

  <-> Answer

  - .
    30 minutes later...

  - Other Officer
    You're not allowed to do that around here.

  <-> Answer

```

In the example above, after moving to **@Answer**, the script flow moves back to **line 14**, continuing after the Channel. The same occurs on line 20.

---
