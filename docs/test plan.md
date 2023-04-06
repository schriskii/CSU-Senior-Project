Introduction
=====

This document lists the tests that will be performed on the plugin. The goal of these tests will be to make sure that users can create menus that fit all of their needs, as per the requirements document found in the same folder as this test plan. Specifically, the menu plugin will be tested, including the part of it that handles controller inputs as well as the actual menu object templates.

Naturally, testing will be conducted using the Godot Engine and a blank test project. Most tests will involve creating a sample menu scene and ensuring that everything works as it should.

Tests
=====

**`A` Create menus with various button layouts and ensure that the automatic neighbor assignments are intuitive.**

Layouts to test:
- Regular grids of buttons
- Vertical and horizontal lists
- Grids of buttons but with some buttons removed
- Grids and lists of buttons but with the positions slightly offset
- Grids / lists but with different sizes of buttons mixed-and-matched

> Results:
> All layouts worked as expected.

**`B` Apply manual neighbor assignments to buttons and ensure that they work properly.**

Create a small grid of buttons, then set the neighbor properties of some buttons and ensure that it overrides the regular position-based cursor movement. E.g. if button A's left neighbor is set to button B, pressing left from button A should highlight button B.

> Results:
> Neighbor system worked as expected.

**`C` Use long text strings for button labels and ensure that strings of reasonable length will fit.**

Test single-line and multi-line strings.

> Results:
> Single- and multi-line strings work as expected. Depending on font chosen, buttons can fit lots of text.

**`D` Move the cursor rapidly and ensure that the button's hovered state updates appropriately.**

Create a menu and move the cursor very quickly back-and-forth. Make sure that buttons don't stay hovered when they shouldn't be.

> Results:
> Cursor states worked as expected even with rapid cursor movement.

**`E` Add many buttons to a menu and ensure that the game doesn't slow down below 60fps.**

Create a 10x10 grid of buttons and move the cursor around.

> Results:
> Large button grids worked as expected. May slow down the game on very poor hardware, but supporting this is out of scope.

**`F` Open 10 menus in the stack and ensure that the game doesn't slow down below 60fps.**

Create a project with 10 menus that link up in a "line" of push references via button on-click actions. Open the whole chain and inspect performnace.

> Results:
> Large menu stack worked as expected.

**`G` Push / pop many menus at once and ensure that it works as expected.**

Create a project and, in code, call the following methods:
- MnoMaster.push_menu_array(), giving it an array of MnoMenu instances.
- MnoMaster.pop_menu(), giving it a MnoMenu instance to pop to (e.g. the title screen).
- MnoMaster.pop_all_menus().

> Results:
> These functions worked as expected.

**`H` Test various menu setups and ensure that input propagation works properly.**

As an easy test, create menu A. Have a button in menu A push menu B. Enable input propagation in menu B's properties. When the confirm button is pressed, a button in menu A should be pressed if the menu B cursor is not hovered over a button. It should not be pressed if the menu B cursor is hovered over a button.

> Results:
> Input propagation worked as expected.

**`I` Switch a button's theme and ensure that all relevant properties (sprite, text field size, etc) are updated appropriately.**

Switch the theme in the editor.

> Results:
> Button theme appropriately updated button properties.

**`J` Test all of the unique button types (toggle, cycle, slider).**

Create various buttons of these three types and ensure that they work properly when their options are changed - cycle buttons should work with any list of options, and slider buttons should work with any range of numbers. 

> Results:
> All button types worked as expected. Cycle / slider buttons work well with a range of different configurations.

**`K` Test the limits of the onscreen button prompt system - how many options can be displayed at once.**

Override MnoMenu.get_button_prompt_list() (as seen in the options demo) with increasing numbers of button prompts until they overflow offscreen.

> Results:
> Depending on string length, 5-15 prompts could be displayed at once.

**`L` Ensure that scrolling lists work properly for various button counts.**

Create a MnoSelectableGroup and make it scroll. Line up lots of buttons and ensure that scrolling always works.

> Scrolling lists worked as expected.

**`M` Ensure that hovering and selecting buttons works with the mouse.**

Use a MnoCursorRenderer with mouse support enabled, and move the cursor around a menu to make sure that hovering and clicking work as expected.

> Results:
> Mouse support worked as exptected.

**`N` Ensure that switching between different controllers works as expected.**

Plug in a controller and make sure that switching between it and the keyboard works properly. Also test with multiple controllers.

> Results:
> Switching controllers worked as expected.

**`O` Ensure that multiple players navigating the menu works as expected.**

Create a MnoMenu and increase the number of cursors. Plug in two or more controllers and test mutliplayer menu navigation.

> Results:
> Multiple cursors worked as expected.
