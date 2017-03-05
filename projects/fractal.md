---
layout: default
title: Fractal
permalink: /projects/fractal/
active: projects
---


# Fractal Renderer

## About

Using CUDA and OpenMPI, I wrote a Madelbrot fractal renderer to run on GPU-accelerated clusters. Using a network of 27 workstations, the following video
was produced by rendering each frame individually with super-sample anti-aliasing and smooth coloring.

Towards the end, the image becomes blocky and fades to a single color when the precision (double) is no longer sufficient to differentiate individual pixels.
The fractal itself actually continues on infinitely.

<div class="row">
  {% include bitbucket.html project="fractalrenderer" %}
</div>

## Video

{% include youtube-player.html video="RsLO87HzuRQ" %}

## Images

{% include imgur-album.html album="t5F5j" %}
