---
layout: post
title: Castles, Trees, and Walk Animations
categories:
- blog
---

This week I worked on a variety of areas in the engine.

First I started on a system for structure generation and rendering.
Right now it uses a template system to build a castle with an instance render for each brick.
Something more clever will be needed going forward, but I was able to drop a (somewhat bland) castle into the Alluvial world.

![Castle](/img/blog/Castle1.jpg)

Still need to amend the forest generation to get rid of those clipping trees.

Speaking of trees, I some experiments with a new procedural tree generation.
I was able to make a more densely polygonated representation of a pine tree, but found it much too busy to replace the existing forest with.
When I get around to supporing multiple tree types in the forest renderer I will probably sprinkle in a few of them.

![New Tree](/img/blog/NewTree.jpg)

The other work I did on the forest system included a way to add slight color variation between instances.
You can see the effect in the castle image above.
Ignore the obvious aliasing issues in the left side of the image - the hash function needs a little work.

The final new feature for the week is a walk animation for the character.
This mostly involved some light repair work on existing skeletal animation code in the engine.
It's a little hard to show in an image but the character's legs now jerk around in an animation that vaguely resembles walking.

![Walk Animation](/img/blog/WalkAnimation.jpg)
