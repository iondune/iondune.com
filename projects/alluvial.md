---
layout: default
title: Alluvial
override_color: "#28b836"
---


## About

Alluvial is an open-world RPG game I am working on in my spare time.
While at university I worked on some prototypes for distant terrain rendering and voxel collision systems.
For my [master's thesis](/projects/relic), I spent two years working on an open-world game engine
with procedural environment generation, a terrain voxel system, and distant forest and terrain rendering.
Since then I have been working on improving those features and expanding the engine.

## Dev Blog

In 2017 I wrote a series of dev blog posts documenting my existing features and new development.
I didn't find it a very effective way to share progress updates on the game, so I stopped making new posts.
But I've archived all of the old posts here:

<ul id="blog-posts" class="posts">
{% for post in site.posts %}
  <li><span>- {{ post.date | date_to_string }} &raquo;</span><a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
</ul>

## Current Screenshots

<div class="row">

<div class="one-third column">
  <a href="/img/alluvial/FeaturesCombined.jpg">
    <img class="img-thumbnail" src="/img/alluvial/FeaturesCombined.jpg" alt="Alluvial Screenshot 1" />
  </a>
</div>
<div class="one-third column">
  <a href="/img/alluvial/VoxelIsosurfaceTerrain1.jpg">
    <img class="img-thumbnail" src="/img/alluvial/VoxelIsosurfaceTerrain1.jpg" alt="Alluvial Screenshot 1" />
  </a>
</div>
<div class="one-third column">
  <a href="/img/alluvial/applet.png">
    <img class="img-thumbnail" src="/img/alluvial/applet.png" alt="Alluvial Screenshot 1" />
  </a>
</div>

</div>


## Old Screenshots

{% include imgur-album.html album="Q2qpa" %}
