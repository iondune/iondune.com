---
layout: default
title: Relic
override_color: "#28b836"
---

## About

Relic is the name I used for the procedural terrain rendering system I built as my Masters' thesis at Cal Poly.

[You can download the full thesis pdf here.]({{ "content/ProceduralGenerationandRenderingofEnvironments.pdf" | relative_url }})

[It is hosted by Cal Poly digital commons here.](https://digitalcommons.calpoly.edu/theses/1678/)

## Screenshots

{% for i in (0..17) %}
{% assign mod3 = forloop.index | modulo: 3 %}

{% if mod3 == 1 %}
<div class="row">
{% endif %}

<div class="one-third column">
  <a href="{{ site.baseurl }}/img/relic/screenshot{{ i }}.png">
    <img class="img-thumbnail" src="{{ site.baseurl }}/img/relic/screenshot{{ i }}.jpg" alt="{{ screenshot.file }}" />
  </a>
</div>

{% if mod3 == 0 %}
</div>
{% endif %}

{% endfor %}
