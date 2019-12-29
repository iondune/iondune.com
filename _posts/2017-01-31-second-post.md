---
layout: post
title: Second post!
categories:
- blog
---

Well, about a month since my last post.
I'm going to give up on writing a comprehensive "what's done" post for now and just write more frequently about what I'm working on.
Pretty much every feature in the engine needs to be revisited at some point, so there will be a good time to talk about everything.
I also want to get into a blogging routine that lines up with my development process.
I'm more or less working on one-week sprints ending on Thursdays, so it would make sense to write on a weekly basis about the focus of those sprints.

Last week I was working on a variety of small features.
At the beginning of the year I had a lot of technology in place but not a whole lot of the actual game features implemented.
That is going to be a core focus over the next few months.
Over the years I have worked on a lot of game prototypes so I thankfully have a few places to pull code from.

One of the main things I pulled into the codebase last week was a tile-based UI system for item inventories.
This makes it possible to drag and drop items not only within a single inventory, but also between two inventories.
For example, you can drag items from your inventory into a chest object's inventory, so that your items are stored for safe keeping.
It also includes some item stacking functionality.

This week I have returned to working on the map/world generator, specifically the terrain and other features.


While I was working on my thesis, I initially experimented with a hybrid approach to terrain generation that used
not only a noise generator but also a finite sampled grid (e.g. a mesh of polygons).
The advantage to this approach is a higher level of control when it comes to placing features (e.g. you can make guarantees
about the size of beaches) that you don't necessarily get when using traditional noise-based techniques.
[Have a look at this article if you're wondering what on earth I am talking about when it comes to a polygonal representation of terrain](http://www-cs-students.stanford.edu/~amitp/game-programming/polygon-map-generation/).

In the end I reverted back to a pure noise representation for simplicity and because I needed to get my thesis out the door by December.
However, now that I am working on the game aspects I am really wanting that higher level of control so that I can place things like villages into the world more easily.
I spent a lot of time working on finding a way to bridge the gap between a large-scale polygonal representation and the fine-grained elevation values I need for the game.
I made some headway on some techniques using [Voronoi diagrams](https://en.wikipedia.org/wiki/Voronoi_diagram) but I think for the time-being I will try a hexagonal or triangular system.
Since this sprint is still in progress I will make another post soon about what I end up doing.
