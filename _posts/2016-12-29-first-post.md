---
layout: post
title: First post!
categories:
- blog
---

I have been working on *Alluvial* for quite some time now, so a dev blog is well overdue.
The current code base started some time around January 2016, but some components are much older than that.
In early 2014, I started writing a simple voxel engine.
As far back as 2011, I was working on [a simple RPG engine](https://www.youtube.com/watch?v=gRFAGwktaRw) using [irrlicht](http://irrlicht.sourceforge.net/).
At the time I was calling it *Relic*.
I think I'll write more about the history of the name and everything in another post, since there is too much to get into here.

*Alluvial* is written in C++ using OpenGL.
More specifically, it is based on [ionEngine](http://ionengine.io/), which is a 3D application framework I have been working on for a few years.
Most of what I have been working on for the past year is the rendering engine, but I have also done some work on physics, character animation, and other components.
To get this blog started out, I'll be writing some posts about the various systems that are already done.

I'm not sure the exact order I'll post them in, but these are the systems I need to write about:

- Far terrain rendering system using geometry clipmaps
- Voxel terrain system using slanted faces
- Forest instance rendering system
- Water surface renderer
- Grid-based physics system

I may have forgotten some, but I'm sure I'll remember as I write more on this blog.