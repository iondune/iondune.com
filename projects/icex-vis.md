---
layout: default
title: ICEX Visualization
permalink: /projects/icex-vis/
active: projects
---


<h1>ICEX - Volumetric Data Visualization</h1>

The below writeup was completed shortly after I finished my first ICEX trip in mid-2013.

<hr>

<h2>Project Overview</h2>
<div class="row">
  <div class="col-sm-6">
    <p>
    My main focus with ICEX was on visualizations of scientific data gathered by the ROV. In this context, "Scientific Data" refers to measurements of temperature, salinity, etc. taken at short intervals (ideally about once per second) during the deployment. We planned to use Smart Tether deta to associate accurate position data with these readings, but didn't account for the fact that the Smart Tether was both poorly designed and ineffective. After localization, we have a large collection of data points with associated sensor readings, and my task was to make these readings visible in a coherent and contextualized manner.
    </p>

    <p>
    This is a project that I've actually already put a lot of work into – this past summer, I worked with Zoe to produce visualizations of data gathered on previous ICEX missions and other projects. One data set I focused on in particular was some oxygenation data sampled from Hopavagen Bay in Norway. I'll be including pictures from that data set in this post as examples of the sort of analysis I'll be doing with the data collected this year in Malta.
    </p>

    <p>
    Starting with the initial data set, one of the simplest visualizations that can be done is simply drawing each individual point from the set. This is often called a point cloud or glyph view. <strong>[1]</strong>
    </p>

    <p>
    This is a straightforward but ineffective way to view the data as a whole. However, it's a good place to start and also a useful addition to any other sort of visualization since it provides the most direct view of the original data set. The next visualization to add is called a volumetric view; it takes on the appearance of a nebulous, transparent cube which is colored to indicate trends within the 3D space of the data measurements. It requires some extrapolation to create, so it's good to include the original data points in this display as well. <strong>[2]</strong>
    </p>

    <p>
    This view makes patterns within the data a bit easier to see, but only on the outer edges of the data range – we can't see what's going on inside the cube very well! Luckily, it's easy to apply transformations to the volume view that allow us to isolate certain features within the data. One example of such a transformation is a slice-by-slice view, but a more interesting way to view the data is by isosurface <strong>[3]</strong>
    </p>

    <p>
    We're getting close to an effective visualization of the data, but we're missing one crucial factor – context! These sensor readings came from a bay in Norway, but you can't tell that by looking at any of the above images. To solve this, we can add in some terrain data acquired from satellite imagery and GIS data sources <strong>[4]</strong>
    </p>
  </div>


  <div class="col-sm-6">
    <div class="row">
      <div class="col-sm-6">
        <div class="thumbnail">
          <a href="{{ "img/content/icex-vis/thumbs/1.png" | prepend: site.baseurl }}">
            <img src="{{ "img/content/icex-vis/thumbs/1.png" | prepend: site.baseurl }}" width="300" class="img-thumbnail">
          </a>
          <div class="caption">
            <strong>1</strong> One small colored cube for each point in the data set. Here, red colors indicate high oxygenation and blue colors indicate low oxygenation.
          </div>
        </div>
      </div>
      <div class="col-sm-6">
        <div class="thumbnail">
          <a href="{{ "img/content/icex-vis/thumbs/2.png" | prepend: site.baseurl }}">
            <img src="{{ "img/content/icex-vis/thumbs/2.png" | prepend: site.baseurl }}" width="300" class="img-thumbnail">
          </a>
          <div class="caption">
            <strong>2</strong> Volume render with point cloud context.
          </div>
        </div>
      </div>
    </div>
    <div class="row">
      <div class="col-sm-6">
        <div class="thumbnail">
          <a href="{{ "img/content/icex-vis/thumbs/3.png" | prepend: site.baseurl }}">
            <img src="{{ "img/content/icex-vis/thumbs/3.png" | prepend: site.baseurl }}" width="300" class="img-thumbnail">
          </a>
          <div class="caption">
            <strong>3</strong> Only areas of the data volume which have a certain sensor value are shown, making it easy to search for internal patterns within the data.
          </div>
        </div>
      </div>
      <div class="col-sm-6">
        <div class="thumbnail">
          <a href="{{ "img/content/icex-vis/thumbs/4.png" | prepend: site.baseurl }}">
            <img src="{{ "img/content/icex-vis/thumbs/4.png" | prepend: site.baseurl }}" width="300" class="img-thumbnail">
          </a>
          <div class="caption">
            <strong>4</strong> Geographic context!
          </div>
        </div>
      </div>
    </div>
    <div class="row">
      {% include bitbucket.html project="volume-rendering-project" class="col-sm-12" %}
    </div>
  </div>
</div>


<h2>Screenshots</h2>
<iframe class="imgur-album" width="100%" height="550" frameborder="0" src="http://imgur.com/a/ho9m5/embed"></iframe>
