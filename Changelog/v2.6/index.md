---
icon: git-commit
order: 6
---
# v2.6

<!-- ![](../../static/img/changelog/2.6.png) -->

**Release Date**: 202Y-MM-DD
**Engine Version**: 5.7

---

!!!
This version is a **work in progress**. It is not yet available for public use.

When a new feature is completed, it will be added to the list. Please note that this is not a complete list of all changes and improvements yet.

New features and improvements are being added regularly, so stay tuned for the final release!
!!!

---

## Scripts

- **Automatically generated labels**, for statements without a manually defined label, are now based on the script ID and the line content. Preserving labels across script edits.
- **Localization keys** now remain the same if the line is unchanged or has a manually defined label. This helps maintain consistency in localization files.

---

## Widgets

- The **Sprite Box** will find the animation by name automatically.

---

## Extras

- <span class="blueprint">(Blueprint)</span> Add the **Get Property Object** utility function
- <span class="blueprint">(Blueprint)</span> Add the **Get Parent Widget of Class** utility function
- <span class="cpp">(C++)</span> Add the **Find Parent Widget of Class** utility function

---

<br />
<br />

## <span class="warning">:icon-alert-fill: Breaking Changes</span>

==- <span class="warning">:icon-alert-fill:</span> Sprite Box Animations
Before updating, make sure the **Sprite Box** animations names match exactly — case sensitive — the name used in script. Otherwise, the animation will not be found.
===

---
