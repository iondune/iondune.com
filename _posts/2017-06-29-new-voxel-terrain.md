---
layout: post
title: New Voxel Terrain
categories:
- blog
---

In my previous post I mentioned that the new voxel system was integrated with the world generation system, so here's a picture of that in action:

![VoxelIsosurfaceTerrain1](/img/blog/VoxelIsosurfaceTerrain1.jpg)

The cool part about this new system is that the materials are layered properly.
The generator has a few rules to determine the depth of different surface types.
So if you dig down underneath the snow, you'll find rock underneath.
Same for finding dirt underneath grass.
That's something that wasn't really possible with the old voxel system, or at least not easy to set up.

The isosurface representation also makes it really easy to tweak the exact shape of the terrain.
There's a little bit of awkward triangulation that I'll be working on going forward, but I'm pretty happy with how it looks already.
I think it looks a lot more organic than the old system, while still including slanted faces that enhance the underlying voxel representation.

More recently I have renewed some work on the forest rendering system.
In particular I am trying to vastly increase the draw distance of large forests.
Right now each tree is represented individually (though with lots of instancing and other tricks) which means that increasing the view distance significantly
will also degrade render performance.
I am working on a GPU raycast system to use for far away areas so that a large theoretical number of trees can be represented efficiently.
More on that soon!
