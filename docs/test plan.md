About
=====

This document lists the tests that will be performed on the plugin.

Tests
=====

**`A` Create various button layouts and ensure that the automatic neighbor assignments are intuitive.**

**`B` Apply manual neighbor assignments to buttons and ensure that they work properly.**

**`C` Use long text strings for button labels and ensure that strings of reasonable length will fit.**

**`D` Move the cursor rapidly and ensure that the button's hovered state updates appropriately, and that the signals are emitted.**

**`E` Add many buttons to a menu and ensure that the game doesn't slow down below 60fps.**

**`F` Open 10 menus in the stack and ensure that the game doesn't slow down below 60fps.**

**`G` Push / pop many menus at once and ensure that it works as expected.**
- Should also test behavior for when the popped-to menu is not present in the stack.

**`H` Test various menu setups and ensure that input propagation works properly.**

**`I` Switch a button's theme and ensure that all relevant properties (sprite, text field size, etc) are updated appropriately.**

**`J` Test all of the unique button types (on/off, list, slider).**

**`K` Test the limits of the onscreen button prompt system - how many options can be displayed at once.**

**`L` Ensure that scrolling lists work properly for various button counts.**

**`M` Ensure that hovering and selecting buttons works with the mouse.**

**`N` Ensure that switching between mouse and controller/keys works as expected.**

**`O` Ensure that multiple players navigating the menu works as expected.**
