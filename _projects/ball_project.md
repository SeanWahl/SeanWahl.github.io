---
layout: page
title: ball-balancing platform
description: an intro to mechatronics
img: assets/img/ballthumb.jpg
importance: 4
category: school
---

In my intro to mechatronics course, we were given a ball-balancing platform and tasked with writing classes and tasks in micropython to be able to properly balance the ball. While no mechanical design was done, it was a great introduction to coding in a python based language and to multitasking.

Throughout the quarter, my lab group had to write classes and functions to be able to use the following actuators/sensors:

    ---
    • dc motors
    • quadrature encoders
    • inertial measurement units
    • resistive touch pads
    ---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/ballthumb.jpg" title="platform" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Here's a picture of the structure and equipment we were provided.
</div>

This was a wonderful overview of mechatronics and a very fun project to work on. We also gained experience creating a user interface to communicate with the Nucleo L476RG, creating state machines, class and task diagrams, data collection, PID control, and multitasking. We were one of two groups to successfully balance the ball on the platform so I am extremely proud of this project and all the work that went into it.

<p align="center">
    <iframe width="315" height="560" src="https://www.youtube.com/embed/BT8gIx_PZtM" frameborder="0" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</p>
<div class="caption">
    Here's a demo of ball balancing in action.
</div>

<p align="center">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/zUB4KfRw6h0" frameborder="0" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</p>
<div class="caption">
    And here's a demonstration of the user interface we created!
</div>

For full documentation of the code written, see <a href="https://seanwahl2023.bitbucket.io/">here</a>.