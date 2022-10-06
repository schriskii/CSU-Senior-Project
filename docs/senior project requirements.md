**`01` The user should be able to place buttons in a menu scene for a player to navigate with directional / button inputs.**
- `Rationale` This is the basic functionality of the plugin.
- `Fit Criterion` The user can place three columns of buttons in a menu and access each one.
- `Type` Functional
- `Priority` 3
- `Prerequisites` 10

**`02` The user should be able to override button neighbor assignments by manually assigning up/down/left/right neighbors.**
- `Rationale` Sometimes the automatic column-based navigation isn't sufficient for odd menu layouts.
- `Fit Criterion` The user can assign another button node to be a neighbor in a button's export variables.
- `Type` Functional
- `Priority` 3
- `Prerequisites` 01

**`03` The plugin includes a custom text scene designed to handle pixel fonts.**
- `Rationale` This will make it easy for users to add outlines and drop shadows to their text.
- `Fit Criterion` The user can instance the scene and create custom text.
- `Type` Functional
- `Priority` 3
- `Prerequisites` n/a

**`04` Buttons should have text labels that the user can edit.**
- `Rationale` Labeling buttons is important for UI design.<sup>[citation needed]</sup>
- `Fit Criterion` The user can assign text to a button.
- `Type` Functional
- `Priority` 3
- `Prerequisites` 03

**`05` Buttons should have states for sitting idle, being hovered, being clicked, and being disabled. Each state should have an animation and a different graphic.**
- `Rationale` Animations and graphics for interacting with buttons makes game menus more intuitive and easier to use.
- `Fit Criterion` The three former states exist and work properly when the player interacts with them. The user can mark a button as disabled to prevent the player from interacting with it.
- `Type` Functional
- `Priority` 3
- `Prerequisites` 01

**`06` Buttons should have signals for being hovered, unhovered, and pressed.**
- `Rationale` Godot's signal system is a common way to have nodes interact with one another. This functionality is important so that the user can assign functionality to a button.
- `Fit Criterion` The three signals exist and are emitted at the appropriate time.
- `Type` Functional
- `Priority` 3
- `Prerequisites` 05

**`07` A menu stack node should exist which allows the layering of several menus at once.**
- `Rationale` This will be useful for multi-layered menu navigation.
- `Fit Criterion` The menu stack node can contain multiple menu scenes, and can push/pop on demand.
- `Type` Functional
- `Priority` 3
- `Prerequisites` 01

**`08` The menu stack should be able to contain many menu scenes at once.**
- `Rationale` Some games will need deep menu trees where the player clicks through many menus to find an appropriate option.
- `Fit Criterion` The menu stack can hold 10 menus without causing slowdown.
- `Type` Capacity, Performance
- `Priority` 3
- `Prerequisites` 07

**`09` The menu stack should support pushing or popping to a specific menu.**
- `Rationale` Some games need shortcuts to other places in the game's menus: e.g. a game may need to send you deep into the options menu, and when the player pops from the stack by pressing the "back" button, it should send them to the outer layer of the options menu, not the menu they were previously in.
- `Fit Criterion` The user can specify a tree of menu scenes to push to the menu stack, or a menu scene to find by popping from the menu stack.
- `Type` Functional
- `Priority` 3
- `Prerequisites` 07

**`10` The plugin should include an input handler to bind controller or keyboard inputs to specific actions.**
- `Rationale` Compared to Godot's native input mapping, this system will give the user more control over behaviors such as buffering and live remapping.
- `Fit Criterion` The node exists.
- `Type` Functional
- `Priority` 3
- `Prerequisites` n/a

**`11` The menu stack should support a universal button to pop from the menu stack.**
- `Rationale` Many games use a universal button, commonly the B button, to go back to the previous menu.
- `Fit Criterion` The user can specify a button, or collection of buttons, to have this behavior.
- `Type` Functional
- `Priority` 3
- `Prerequisites` 07, 10

**`12` Menu scenes should be able to specify whether or not they allow inputs to propagate down the menu stack.**
- `Rationale` Most of the time in a game, inputs should not be allowed to reach menus other than the one at the top of the menu stack (since that is just the previous menu the player accessed). Sometimes, however, an overlay menu may require inputs to propagate downward.
- `Fit Criterion` The user can specify this behavior for each menu scene, for both incoming and outgoing inputs, as well as on a per-input basis. Also, the user can access A) the initial (pre-propagation) input state and B) the final (post-propagation) input states.
- `Type` Functional
- `Priority` 3
- `Prerequisites` 07, 10

**`13` The plugin should be adequately documented.**
- `Rationale` Documentation is good.<sup>[citation needed]</sup>
- `Fit Criterion` The code is commented, and a readme is included with the plugin as a usage guide.
- `Type` Usability / Personalization
- `Priority` 3
- `Prerequisites` n/a

**`14` Example pixel art graphics should be included with the plugin.**
- `Rationale` Example graphics will help users understand how the plugin should be used and help it work out of the box.
- `Fit Criterion` A graphic is included for each of the four key button states.
- `Type` Functional
- `Priority` 3
- `Prerequisites` 05

**`15` The user should be able to create and select custom button themes.**
- `Rationale` In a game, different buttons often require different graphics and animations.
- `Fit Criterion` The user can create different button themes and select them in a dropdown for each button.
- `Type` Functional
- `Priority` 2
- `Prerequisites` 14

**`16` Buttons should have a fifth state for when the button is hovered but not at the top of the stack.**
- `Rationale` For certain menus, having this state would be useful for UI clarity.
- `Fit Criterion` The fifth state is implemented and has its own graphics.
- `Type` Functional
- `Priority` 2
- `Prerequisites` 05

**`17` The plugin should include an on-off toggle button.**
- `Rationale` Toggling an option on and off is a common UI element in games.
- `Fit Criterion` There is a scene that extends the basic button with this functionality.
- `Type` Functional
- `Priority` 2
- `Prerequisites` 01

**`18` The plugin should include a button to select options from a list.**
- `Rationale` Selecting from a list of options is a common UI element in games.
- `Fit Criterion` There is a scene that extends the basic button with this functionality.
- `Type` Functional
- `Priority` 2
- `Prerequisites` 01

**`19` The plugin should include a button that acts as a slider.**
- `Rationale` Selecting a number value on a slider is a common UI element in games.
- `Fit Criterion` There is a scene that extends the basic button with this functionality.
- `Type` Functional
- `Priority` 2
- `Prerequisites` 01

**`20` The menu stack should have an option to display button prompts onscreen.**
- `Rationale` Onscreen button prompts are a common element in games which help with accessibility and ease-of-use.
- `Fit Criterion` The menu stack node displays text and symbols along the bottom of the screen which show button prompts such as "B to go back", "A to select", etc. Menu scenes that are accepting inputs can supply prompts to be displayed here.
- `Type` Functional
- `Priority` 2
- `Prerequisites` 07, 10

**`21` There should be an option to create scrolling lists of buttons.**
- `Rationale` In situations where not all buttons fit onscreen at once, a scrolling list is useful.
- `Fit Criterion` The user can create columns of buttons that scroll vertically.
- `Type` Functional
- `Priority` 1
- `Prerequisites` 07

**`22` The menus should have mouse support.**
- `Rationale` This plugin is designed for games that use a controller, but mouse support is always nice.
- `Fit Criterion` The player can navigate the menus with a mouse. Hover states and such work appropriately.
- `Type` Functional
- `Priority` 1
- `Prerequisites` 01

**`23` The menus should support multiple players navigating a menu at once.**
- `Rationale` This could be useful for certain menus in multiplayer games.
- `Fit Criterion` Each player has a cursor to navigate the game's menus. A menu scene can be specified to either support or not support multiple cursors.
- `Type` Functional
- `Priority` 1
- `Prerequisites` n/a

**`24` The menu scene should come with animations for opening/closing the menu.**
- `Rationale` Opening a new menu with no transition would be jarring. A swipe, fade, etc. makes menus feel much more professional and polished.
- `Fit Criterion` The user can specify which animation a menu should have when opened or closed.
- `Type` Functional
- `Priority` 1
- `Prerequisites` 07
