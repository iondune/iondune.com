---
layout: post
title: Inventory Rewrite
categories:
- blog
---

This week I rewrote a lot of the inventory code.
I had written a small UI toolkit a few years back that supported dragging and dropping icons into slots.
I imported it into Alluvial at the beginning of the year to give me something to work with, but there were a few problems with it.
In particular the library style of creating and destroying "slot" and "tile" objects was a little bit cumbersome to work with.
A kind of tricky event system was needed to add and adjust tiles when an item was added to the player's inventory while the inventory menu was open.
It was also easy to make a small mistake that caused a crash when, for example, trying to add an item to an existing stack contained within a different actor's inventory.
In short, the system worked fine but from a programming perspective it was annoying to work with and add new features to, meaning it was bad for development.

So, I completely rewrote the UI toolkit to use the "immediate mode" style of UI creation.
If you're curious what I mean, [Dear Imgui](https://github.com/ocornut/imgui#references) is a really good example of an immediate-mode UI toolkit.
For those who aren't software developers, it suffices to say that the new system is more robust and makes it easier to add new features to the game.

Here's a picture of the new inventory!

![Inventory](/img/blog/Inventory.jpg)

I also did some work on a content creation app to make it easier to add new items to the game.
One of the cool features is that the item icons are rendered using the in-game mesh.
It's super easy to make small adjustments to these icons, such as zooming out a bit to show more of the hammer, and have those changes automatically show up in the game.
