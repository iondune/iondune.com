---
layout: post
title: Mind The Gap
categories:
- blog
---

Back again after another long pause in development.
My teaching schedule and the courses I was working on made it difficult to find time to work on Alluvial during the Spring quarter.

But the good news is that Summer is here and I'm ready to focus on Alluvial full time.
While I didn't get a lot of coding done over the last few months I did spend a lot of time thinking about the voxel system and decided to change things up a bit in order to solve a lot of on-going problems.
The old system based on my thesis work didn't have a good way to represent multiple materials, among other problems.
The new system that I have been working on this week is based on dual isosurface extraction algorithms and offers a high degree of control while also generating surfaces that I think look much more organic than what I had before.

![DualVoxelation](/img/blog/DualVoxelation.png)

The dual voxelation is almost fully integrated into the world generation at this point.
Actually, it's probably fair to say that it *is* fully integrated in the sense that it is doing everything that the old system could do.
But, I still need to work in some of the features that are now far more possible with the new system.
In particular, I'm working on a scheme for layering different materials (e.g. snow on top of stone in the mountains, grass on top of dirt in the forests).
Once that is done I'll post a new update with some images of the integrated terrain!

---

There are a few other things planned for the summer that I'll be announcing and starting shortly.
Soon this blog won't be the only way to keep updated on Alluvial's progress!
