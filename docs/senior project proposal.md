Student Name:
=============

Chris Koenig

Degree & Major:
===============

Computer Science, B.S.

Project Advisor Name:
=====================

Sean Hayes

Expected Graduation Date:
=========================

May 2023

Problem Statement:
==================

In video game development, almost any game will need some sort of user interface
to select gameplay modes and options. Ideally, then, game developers should have
access to an easy, templated way to create menus for their game. However, the
default options that come with game engines are not right for every game. Godot,
for example, has a default UI system, but it is somewhat obtuse and has features
that can get in the way of games with simpler needs - e.g. its mouse support can
get messy for controller-only games.

My project implements a custom UI system into Godot, which makes it quick and
easy for game developers to create menu systems. It also implements a stack,
created to allow easy implementation of layered menu trees, e.g. an environment
where the user needs to dig into various sub-menus to find options. Lastly, it
includes a framework to handle controller and keyboard input, which can then be
used to control the rest of the game - not just the menus.

Project Description:
====================

My project will consist of a selection of Godot scenes and scripts that allow the
game developer ("user") to easily and quickly create menus in their Godot games.
It will consist of the following components.

**Menu buttons:** There will be a menu button scene, with states for being hovered
over, being clicked, and being disabled. When the player clicks the button, it
will emit a Godot signal that other code can then hook onto to perform actions.
There will also be specialty buttons for common tasks, such as toggling a value
on/off or selecting from a list; these will inherit from the regular button.

**Menu scenes:** These buttons will be contained inside menu scenes, which allow the
arrangement of buttons on the screen according to the user's wishes. These scenes
can hold any other Godot objects too, such as onscreen graphics. They could be
used for heads-up display elements, not just proper menus.

**Menu stack:** These menu scenes will be contained inside a menu stack, which is a
constantly-loaded object that maintains a stack of menu scenes. When the player
clicks a button to open a new menu, it gets placed at the top of the stack, and
when the player presses the "back" button, the top element of the stack will be
popped. This maintains navigation logic similarly to a file explorer's address
bar. The user will be able to control specific behaviors such as whether or not
inputs are allowed to propogate down the stack (on a per-menu basis).

**Input controller:** There will also be an object to handle controller and keyboard
input. Compared to Godot's built-in input mapping system, this object will allow
the user to more precisely define behaviors such as input buffering, as well as
to change the input mapping while the game is running (useful for implementing
custom controls in a game). This will be used for the menus but can also be
referenced by other code to, for example, control the player character.

Proposed Implementation Language:
=================================

GDScript

Libraries, Packages, Development Kits, etc:
===========================================

Godot Engine

Additional Software/Equipment Needed:
=====================================

GitHub

Personal Motivation:
====================

I make games as a hobby and have been working on a versatile foundation for my
games in my free time. All of the menus in my games so far have been quick,
bodged-together solutions. This project would give me a way to avoid redundancy
in my code, increasing maintainability and flexibility.

Outline of Future Research Efforts:
===================================

For this project, I will need to research the various kinds of engine extension
available in Godot and determine how this project should be packaged.

Tentative Schedule:
===================

October 15, 2022:
- Choose a broad implementation plan within Godot (e.g. module? extension?)
- Implement the four main components on a basic level: one menu at a time, only basic buttons.

October 31, 2022:
- Implement a second button type.
- Implement button theme switching.
- Implement menu stack behavior with >1 menu.

November 15, 2022:
- Wrap up development by implementing any remaining functionality.
- Finish test plan.

April 30, 2023:
- Complete and present defense documentation.
