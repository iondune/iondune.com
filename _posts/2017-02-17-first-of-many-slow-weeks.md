---
layout: post
title: First Of Many Slow Weeks
categories:
- blog
---

Had a bit of a slow week this sprint for a variety of reasons.
Mostly material prep for my course at cal poly and good ol' fashioned procrastination.

One of my main goals for this week was to start fixing the "floating object" problem.
The collision system currently deals with three distinct types of objects.
The first and simplest are items, which simply bounce off of other collideable objects.
The second is actors, which represent moving characters that can fall and move around the world.
The third kind of object is static objects, which includes things like trees and the bricks that make up the castle.

Most of the time, static objects don't move at all, so I wasn't simulating any sort of interaction for them.
However, if you dig underneath a tree or try to knock down a castle, those static objects need to come to life.
In this sprint I added some functionality to allow static objects to fall to the ground if they aren't supported.
It's not perfect and there are a lot of additional cases to be handled, but it's a good start.
Now if you dig the ground underneath a tree, it will slide further into the ground.

![Tree Digging](/img/blog/TreeDigging.jpg)

And yes, adding shadows and different shading for grass surfaces and excavated dirt are both on the radar.
It's a little hard to see what's going on in the above screenshot without those features.
