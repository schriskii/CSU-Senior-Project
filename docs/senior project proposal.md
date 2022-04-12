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

In an online video game, input lag (the delay between pressing a button and the
onscreen action being performed) should be kept as low as possible for a smooth
and pleasant playing experience. However, the need to keep the game calculations
in sync for both players means that if the network connection has latency, input
lag must be increased to compensate. This input lag, if severe enough, can ruin
many timing-based action games. For example, *Super Smash Bros. Ultimate*
was excluded from a prominent online fighting game tournament for this reason (1).
“Rollback netcode” largely solves this problem but requires changes to the
structure of a game's source code. My project implements rollback netcode as
an extension to Godot, a game creation framework. My implementation will be
easy and intuitive so that it can be tucked behind the scenes. Therefore, new
game developers, such as myself, will be able to take advantage of rollback
netcode without having to implement it manually.

1.  https://www.thegamer.com/smash-ultimates-netcode-too-bad-evo/

Project Description:
====================

Rollback netcode is a type of network coding which avoids input lag. With a slow
connection, rollback does not introduce a large input delay to account for the
network latency. Instead, if it has not yet received a signal, it predicts that
the other player will not press any buttons (or stop holding any buttons) and
continues to process the game state. If an update arrives and the prediction
turned out to be false, the game "rolls back", rewinding to the last time the
two clients were in sync, and then re-processes those game ticks with the new
information. In other words, instead of waiting for the other player's input
data, it ignores the missing data and then corrects any mistakes that pop up.

My project will be a Godot engine module that handles saving game states,
syncing two clients over the network, and reloading/resimulating game states. It
will efficiently store game state information in an internal data structure and
expose it to the user for reference when needed. It will also use existing Godot
infrastructure (2) to communicate with clients over the network and handle
rollback netcode according to the procedure described above. Users will be able
to connect to the module's API to trigger rollbacks manually, determine which
game state data should be logged, and execute additional code when a rollback
occurs.

2.  https://docs.godotengine.org/en/stable/tutorials/networking/high_level_multiplayer.html

Proposed Implementation Language:
=================================

C++

Libraries, Packages, Development Kits, etc:
===========================================

Godot Engine

Additional Software/Equipment Needed:
=====================================

Visual Studio Code, GitHub

Personal Motivation:
====================

I make games as a hobby and have been working on a versatile foundation for my
games in my free time. I would like to be able to easily add online play to my
games in the future. In particular, one of my dream projects is an online
fighting game, and in that genre, rollback is quickly becoming an expected
standard thanks to the snappy online gameplay it offers. Also, this will be a
great opportunity to learn about networking in general.

Outline of Future Research Efforts:
===================================

For this project, I will need to learn how to make Godot modules in C++. I will
also need to research Godot's networking options more in-depth and find the best
fit for my purpose. Lastly, I will need to find the best way to optimize the
relatively large amounts of memory read/write required for this task (aided by
the use of C++ instead of Godot's standard Python-style GDScript).

Tentative Schedule:
===================

April 12, 2022:
- Develop the system for saving and reloading past game states.

August 31, 2022:
- Research Godot's native networking options and find the best fit.

September 30, 2022:
- Implement rollback netcode.

October 31, 2022:
- Flesh out the user-end API.
- Develop test plan.
- Begin to test the module within my work-in-progress games as well as dedicated testing projects.
- Begin to evaluate test results.

April 30, 2023:
- Complete and present defense documentation.