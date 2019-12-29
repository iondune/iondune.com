---
layout: post
title: More Work On Terrain Features
categories:
- blog
---


[Back in a previous sprint](/blog/2017/02/03/world-grid-experimentation.html) I was working on a new terrain generation system using an interpolation grid.
This week I started working on the terrain feature generators that will be used in conjunction with the grid system.
The first feature I worked on was mountains - these look a lot like the mountains I have been generating, but with more control of the height and shape.
I use some polygonal geometry as the basis of the mountain shape and to influence the noise-based generation.

![MountainFeature](/img/blog/MountainFeature.jpg)

I also made some progress on a shoreline feature, that can generate cliffs around the eges of lakes.
Here's a debug view that uses bright colors to indicate different parts of the shoreline.

![ShorelineGeneration](/img/blog/ShorelineGeneration.jpg)

The main advantage of this new system is increased control over the terrain, from a developer's perspective.
The existing, old terrain system relies on a lot of magic numbers and formulas to create the transitions between different terrain types.
This makes it really difficult to add in new terrain features, or even make tweaks to the existing ones.
By using a interpolated grid to place feature geometry, then have individual generators tied to each piece of geometry,
I will not only be able to do more interesting things with the generators I already have (e.g. mountains, shorelines),
but also be able to add new generators without having to worry about messing up the old ones.

This next sprint might be a slow one due to the timely release of [Breath of the Wild](https://en.wikipedia.org/wiki/The_Legend_of_Zelda:_Breath_of_the_Wild).
At least I can argue that I'm doing research on games that are related to Alluvial :)
