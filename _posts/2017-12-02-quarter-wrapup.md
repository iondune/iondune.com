---
layout: post
title: Quarter Wrapup
categories:
- blog
---


For a variety of reasons, this quarter at Cal Poly has been a busy one for teaching.
As a result I didn't make a whole lot of progress on the game.
However, I did find some time to work on a few various pieces of the engine over the last few weeks.

First off, I finished up work on the initial object system refactor effort I discussed at the end of the last blog post.
Prototypes in the game database now represent a class of objects with similar characteristics,
but object-specific properties are capable of changing things like the collision shape and mesh.
Specifically this lets me have a single entry in the database to represent "wood beams,"
and a "Height" property of each object specifies the size of the collision volume and the shape of the mesh.


While working on the database, I added a mesh preview to the Database Editor program so that I could preview
the effect of changing various properties on the mesh of the object.

![database editor applet](/img/blog/applet.png)

This is using a new "applet" interface I am adding to the engine,
to make it easier to debug certain features by opening an application within an application.
The eventual goal of this feature is to be able to open up all the tools I have been working on,
like the world map preview and the database editor, while I am testing the game or some other
part of the engine.

With the object overhaul done, I started work on implementing some game rules in the engine.
I made it so that looking at an object displays the object name as well as a health bar.

![healthbar](/img/blog/healthbar.jpg)

Hitting an object reduces its hitpoints.

![damaged](/img/blog/damaged.jpg)

And reducing an object's hitpoints to zero removes the object from the game.

![destroyed](/img/blog/destroyed.jpg)

I haven't implemented anything particular interesting for the destruction of an object
(such as dropping relevant crafting materials or any particle effects)
but at least for now, destroying a chest will drop the items that were in the chest
as well as a wood chunk.

In general I have also been making minor tweaks and fixes around the engine.
For example, I fixed a long-standing bug that made it annoying to pick up items:
the item bounding box was always close to where an object was, but never quite what you expected.

---

The Fall quarter at Cal Poly is coming to a close, so after I'm done grading projects and finals
I should have more time over the winter break to get more work done!
Plus, the two classes I'm teaching in the new year should prove to be a lighter workload.
We'll see.
