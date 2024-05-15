---
layout: post
title: touch extender
date: 2024-05-15 12:00:00
description: for touching touch screens
categories: 3Dprinting
thumbnail: assets/img/touch2used.jpg
images:
  compare: true
  slider: true
---

My car has a touch screen for its media system. This is great, but my girlfriend does not like leaning forward to touch the screen to skip songs. Obviously there had to be an easier way to do this. So I made a touch extender.

<div class="row">
    <div class="col-sm">
        {% include figure.liquid loading="eager" path="assets/img/touch1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The first iteration of the touch extender. Essentially a gloved piece of plastic at the end of a stick.
</div>

There were two problems with this first version. The first problem was that the structure consisting of a thin wooden stick made the extender really flimsy and especially prone to buckling.

<div class="row">
    <div class="col-sm">
        {% include figure.liquid loading="eager" path="assets/img/touch1bend.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The first version bent easily and was prone to vibrating. This was no good in terms of feel and accuracy.
</div>

The second (and much larger) problem was that the screen in my car is a capacitive touch screen, which I forgot to consider initially. The touch screen needs to pick up a charge to detect a change in capacitance, which a glove on a piece of plastic cannot do. To combat this, I bought a very cheap phone stylus to check if I could easily overcome this.

<div class="row">
    <div class="col-sm">
        {% include figure.liquid loading="eager" path="assets/img/touch1modified.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    I attached the stylus to the end of the original extender and then electrically connected the handle to the stylus. In testing, this worked on the touch screen.
</div>

Now that I had a working solution, I decided to fix both problems and make the design much more robust for fun. The end result is cataloged below.

<swiper-container keyboard="true" navigation="true" pagination="true" pagination-clickable="true" pagination-dynamic-bullets="true" rewind="true">
  <swiper-slide>{% include figure.liquid loading="eager" path="assets/img/touch2frontview.jpg" class="img-fluid rounded z-depth-1" %}</swiper-slide>
  <swiper-slide>{% include figure.liquid loading="eager" path="assets/img/touch2backview.jpg" class="img-fluid rounded z-depth-1" %}</swiper-slide>
  <swiper-slide>{% include figure.liquid loading="eager" path="assets/img/touch2hand.jpg" class="img-fluid rounded z-depth-1" %}</swiper-slide>
  <swiper-slide>{% include figure.liquid loading="eager" path="assets/img/touch2handle.jpg" class="img-fluid rounded z-depth-1" %}</swiper-slide>
  <swiper-slide>{% include figure.liquid loading="eager" path="assets/img/touch2used.jpg" class="img-fluid rounded z-depth-1" %}</swiper-slide>
</swiper-container>
<div class="caption">
    The new design features 3 wooden posts, a real handle, and the stylus. The wooden posts are intermittently supported to make the design much stiffer. The handle is wrapped in wire that feeds to the stylus to carry charge to the touch screen. All connections are superglued, as strength is not a large concern in this application.
</div>