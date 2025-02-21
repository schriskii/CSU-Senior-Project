# Mno Menus

May 2023

Scott "Chris" Koenig

Computer Science

Dr. Sean Hayes

## Statement of Purpose

In video game development, almost any game will need some sort of user interface to select gameplay modes and options. Ideally, then, game developers should have access to an easy, templated way to create menus for their game. However, the default options that come with game engines are not right for every game. Godot, for example, has a default UI system, but it is somewhat obtuse and has features that can get in the way of games with simpler needs - e.g. its mouse support can get messy for controller-only games, and the way its graphics work can impede certain art styles such as pixel art.

My project implements a custom UI system into Godot, which makes it quick and easy for game developers to create menu systems. It also implements a stack, created to allow easy implementation of layered menu trees, e.g. an environment where the user needs to dig into various sub-menus to find options. Lastly, it includes a framework to handle controller and keyboard input, which can then be used to control the rest of the game - not just the menus.

## Research and Background

I have a history of making game projects in Godot, so not that much preliminary research was required. I did need to investigate the different types of Godot plugin, and settled on writing mine in GDScript.

## Project Language, Software, and Hardware

The project was created in Godot 3.x using its GDScript programming language. All of the code was written using the Godot Engine editor, and the class icons were created in Aseprite.

## Project Requirements

See [project requirements document](<./senior project requirements.md>).

## Project Implementation Description and Explanation

![Screenshot of the plugin](<./mno menus screenshot.png>)

*Fig. 1 - A screenshot of the plugin being used in the Godot Engine editor.*

This is a plugin for use in the Godot Engine editor, used to create menus for selecting options in a game. The user can create menu scenes and add buttons to them, then use code to instantiate in the game.

See [code repository](https://github.com/muno777/mno_menus) for further documentation, including a quick start guide.

## Test Plan and Test Results

See [test plan document](<./test plan.md>) (which includes test results).

## Challenges Overcome

The biggest challenge when creating this project was managing the scope of the codebase and making sure that all of the parts work together nicely. In particular, because Godot 3.x doesn't support cyclical class references in its code, I had to work around it in somewhat awkward ways.

## Future Enhancements

In the future, I'll be remaking this project in Godot 4 for use with my future game projects. Along the way, I'll tidy up some of the organization and structure of the code.

## Defense Presentation Slides

See [slideshow](https://docs.google.com/presentation/d/1FsIsOjYohLYRDzRfXj20DSDJWtEGFXfYjdSsbLqCaUA/edit?usp=sharing).
