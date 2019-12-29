---
layout: post
title: World Grid Experimentation
categories:
- blog
---

This week I finished some initial work on a new world generation system.
I experimented with voronoi, hexagonal, and cartesian grid basis and interpolation.

![World Grid Examples](/img/blog/WorldGridExamples.png)

I spent a while thinking and prototyping solutions to interpolation on voronoi and hexagonal grids.
In order to generate transitions between different terrain types, I need a way to detect when a given area is, say, 50% forest and 50% field.
This means I need a way of smoothly evaluating the world grid.
In particular I want a interpolation of grid values with continuous first and second derivatives.
For a square, cartesian grid, there is a simple solution to this problem: bicubic interpolation.
With voronoi I made some headway using a modified version of Inigo Quilez's smooth voronoi algorithm.
However, I had some issues with regions defined by very nearby voronoi sources.
In these areas the interpolation would be stretched over a larger area.

![Voronoi Interpolation](/img/blog/VoronoiInterpolation.jpg)

This wasn't quite what I wanted, so I started working on a modified solution using Inigo's accurate edge distance method.
But at this point I realized I was sinking a lot of time into a rather deep technical problem.
To keep myself motivated and to make sure the project keeps rolling, I'm trying to avoid doing that.
So before I spend more time working on the voronoi system, I'm going to prototype the rest of the generation system using a cartesian grid.
A lot easier to do interpolation and other geometric reasoning with that datastructure, and arguably the only downside is horizontal and vertical artifacts in the output.

There's a lot still to do, but I'm trying to avoid focusing too much on any one feature.
For now I'm putting off the terrain generation while I focus in on other features.
