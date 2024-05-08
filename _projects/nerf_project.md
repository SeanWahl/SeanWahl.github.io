---
layout: page
title: nerf turret
description: a heat-seeking projectile launcher
img: assets/img/nerfthumb.jpg
importance: 3
category: school
---

For my intermediate level mechatronics course, our term project was to duel using autonomous nerf guns across a table. We were given a Nucleo L476RG, an infrared camera, and two motors with encoders. We were left to our own devices to source a nerf gun, make a structure for the system, and write the code for the dueling scenario. 

Though our mechanical design was hasty, it was an advantage because we had more time to tune our system. We designed and manufactured it as a group with most of the structure being wood besides a lazy susan, an aluminum axle, skate bearings, and 3D printed gears/pulleys. We analyzed the system dynamics and ran them in a Jupyter Notebook script to determine a proper gear ratio for the system to turn around quickly but accurately.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/nerfthumb.jpg" title="full turret" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Our final turret.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/nerfbase.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Taking a closer look at the base, you can see how the 3D printed gear fits on the heading motor and interfaces with the internal gear.
</div>


The nerf gun we purchased was electronically activated via a limit switch and would spin up two flywheels before feeding nerf darts into the wheels. We hotwired this so that two separate GPIO pins could activate the flywheels and feed mechanism separately. The feed mechanism signal didn't draw power directly from the GPIO pin, but the flywheels did. To deal with this I used a spare relay to activate the flywheels using the GPIO pin as to avoid frying the microcontroller.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/nerfelectrical.jpg" title="electronics" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Nucleo L476RG interfacing with the two motors. The relay is not visible from this angle. It is of note that the system could not turn 360 degrees without tangling wires.
</div>

With the full system set up, it's a good time to mention the rules of the competition. The teams would have a representative at one end of the table, guarded by their nerf turret. Upon a signal, the nerf guns would turn 180 to face the other side of the table. The opponent has 5 seconds to move around on the other side followed by 5 seconds of standing still. 

The infrared cameras we were using took about 0.4 seconds to take a picture when running micropython, so speed tracking was not possible. For this reason, our robot waited until the moving period ended and then tried to shoot them while standing still. Our camera was placed halfway down the table for increased resolution and our system was controlled by a PD controller. If we were running in C we could've likely tracked the target in real time, but this wasn't a possibility with what we were given.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/nerfsketch.jpg" title="table geometry" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Table sketch used to convert camera pixel data into a usable angle to aim at. The full camera resolution was something like 32x32 pixels. The table took up pixels 7-25 horizontally and this was used in a correlation with corresponding angles in order to track the opponent's heat signature.
</div>

<p align="center">
    <iframe width="315" height="560" src="https://www.youtube.com/embed/JCTmFaLQwpU" frameborder="0" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</p>
<div class="caption">
    Here's a demo of the working nerf turret before we raised the shooting pitch.
</div>

This was a very fun project to be able to work on and I value what I learned from working on it. In the end, we lost in our second round of dueling to a team that wasn't able to shoot because we got -1 point for missing our shot... That's just the way the world works I guess!

For solo website portfolio of this project, see <a href="https://seanwahl.github.io/ME405_TermProject/">here</a>.