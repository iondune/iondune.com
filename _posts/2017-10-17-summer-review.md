---
layout: post
title: Summer Review
categories:
- blog
---

I haven't posted to this blog in a while, but thankfully this time it's because I've been busy working on Alluvial!
And then this post got put off for a while because of the start of a new quarter...

But, anyway!
To get things back up to date, I'm going to dig through my mercurial history to record what I did every week since the last update.

My last post about game content was June 29th, the middle of "Week 2" of my summer.
So, I'll start at the rest of Week 2.



## Week 2

- Some work on some possible new forest rendering avenues.
  I would really like to have some sort of volumetric ray cast system for distant forests,
  but so far getting something that looks nice has seemed like it will be very time consuming.
  In the short term, I plan to just increase the tree size (trees right now are much too small, so more of them are needed to cover distant terrain)
  and work on lowering the detail of distant trees.
- Some refactoring in ionEngine, mostly just moving some things around for better organization.
  Remember that ionEngine is open source, so you could go take a look at those changes if you wanted to!

![forest screenshot](/img/blog/review/ForestHills.jpg)


## Week 3

At this point I started a big push on improving the terrain generation engine.
In particular, I was interested in adding some global processes based on analysis of the entire map, for things like drainage basins and rivers.
At first I tried analyizing the existing cubic interpolated heightmap to place river nodes,
but it quickly became apparent that a graph-based approach would be both far faster and make it easier to control the results.


## Week 4

At the start of this week I did some work on incorporating water into the voxel terrain system.
It's very rudimentary at this point - basically just solid blue voxels where water should be.
But this gave me the ability to have water at different elevations, e.g. for rivers.

![water voxels](/img/blog/review/WaterVoxels.jpg)


On the terrain generation side of things, I dove into polygonal map-based generation.
I worked on generating a [half-edge representation](http://www.redblobgames.com/x/1722-b-rep-triangle-meshes/) of some existing voronoi diagram generation code I had been using.
This wasn't as straightforward as I hoped it would be, so I spent a while working on some tools to visualize my terrain graph.

![graph edges](/img/blog/review/GraphStructure.png)


## Week 5

At the start of this week was some ongoing effort to generate a complete half-edge representation of my graph.
I was primarily having issues with weird edge cases at the corners of the graph, where there were duplicate edges.
This wouldn't really be much of a problem except it caused an infinite loop in some of the map generation algorithms.

Once that was resolved I did some work on generating terrain using the polygonal map.
This included using an elevation noise layer to generate landmasses, then building polygon strips along the shorelines.

![land mass and shorelines](/img/blog/review/LandMasses.png)


## Week 6

Started work on adding rivers to the world map.
One of the main motivations for the polygonal graph structure was that it makes adding rivers
a lot more straightforward and especially a lot more controllable.
I experimented with using the rivers to set terrain elevation, but while this was an interesting emulation of
real-world terrain generation (i.e. by errosion) it proved to be too difficult to control.
I improved a 3D preview of the world map,
and tried polygonal cubic interpolation for elevation on the map.
I was able to get the interpolation semi-working, but if I end up using it for the game
I will need to do some additional work.

![river polygons](/img/blog/review/RiverPolygons.png)


## Week 7

Started this week with some work on adding non-terrain elements to the map, e.g. castle and village locations.
Then with that in place, I returned to structure generation:
mesh generation tools and structural layout generation to create village houses.

![village map](/img/blog/review/VillageMap.png)


## Week 8

I was out of town this week so I spent some time on the Linux build configuration (so I could develop on a lightweight chromebook).
The game itself won't run on a chromebook... it's far too CPU and GPU intensive.
But a lot of the development tools I've been making definitely do!

Some work on what I call the "Database Editor", a program that lets me work on the item database for the game.
I also started some work on a "Mesh Editor" program to make it easier to import models into the engine.

![hammer selected](/img/blog/review/MeshEditor.png)


## Week 9

Kind of a slow week since I was out of town, but I did some work on the Mesh Editor and also made some tweaks to the terrain generators.

![mountain hills](/img/blog/review/MountainHills1.jpg)


## Week 10

Spent this week working primarily on the terrain generation features.
Soem work to make rivers look better, adding hilliness to the mountain generator so the transition between flatland and mountains was less erratic.

![mountain hills](/img/blog/review/MountainHills2.jpg)


## Week 11

A lot of commits this week across a variety of components.

- Some ongoing improvements to the game item database and the related mesh editor.
- Added shoreline cliffs and some "base elevation" noise to terrain generation.
- Started a floorplan generation system for creating interesting large structures, such as castles.

![floorplan](/img/blog/review/Floorplan.png)


- Some work in the collision system to better support the added structure shapes, in particular for picking and
  destruction.
- Some initial work on supporting objects with procedural mesh generation (instead of just `.obj` import).

![high-frequency noise voxels](/img/blog/review/HighFrequencyNoise.jpg)


## Week 12

![stairwell](/img/blog/review/Stairwell1.jpg)

A few minor additions and work this week, such as cleaning up the stair-well generation code for castles
and adding drag-and-drop support to the mesh editor.

![stairwell](/img/blog/review/Stairwell2.jpg)

Then, I started a big overhaul to the game item database system.
I have been using a prototype-based object system in which each object has an immutable prototype that
defines its attributes, such as what mesh to use, the in-game visible name, and what type of collision entity it has.
The problem with this approach was that certain types of objects could come in a wide variety of sizes,
for example the "wooden support beam" used in construction of houses.
This meant I had to programmatically create a lot of duplicate prototypes in the database, e.g.
"wood beam 1x1", "wood beam 2x1", "wood beam 3x1", etc.

So I started a large refactoring effort to make the prototype system more general purpose.
In particular I'm making it so that each object can have an expandable set of attributes that affect
things such as how it is rendered and what the object can be used for.

A good example of how this ties nicely into the procedural nature of the game is coins.
In this early prototyping stage of the game, I had two different types of coins: "gold coins" and "copper coins".
When the overhaul is done, however, I'll only ever need one coin prototype in the database.
Every other detail can be handled with attributes, such as what material the coin is made of,
what government entity created the coin, and what denomination it has.
