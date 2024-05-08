---
layout: page
title: offset link
description: 3D printing for strength
img: assets/img/link.jpg
importance: 5
category: school
---

When I was just learning design for strength and stiffness, I was given a project to design an offset link to hold 500N in tension between two pins. On top of this, there was a bisecting keep-out area in the middle of the joint. The link we designed had to be 3D printed out of PLA.

In a team of 4, we researched the material properties of PLA and the effects of print infill and print orientation on these factors. There wasn't too much definitive data to use in our exact case so we conservatively estimated these values from our sources.

We sized the link with a small safety factor above the desired load. We chose a sleek design that worked well in tension without too much unnecessary material. Not only were we trying to sustain the load but also to have the lowest weight. We did calculations for the critical stress state of the link (ignoring fatigue), the estimated deflection at the given load using Castigliano's method, and hedged against various failure modes, such as shear tearout and bearing failure.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/link.jpg" title="link" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This is the design we chose for the link.
</div>

Due to all of the assumptions we conservatively made throughout the process, our link ended up sustaining 300% of the load (1500N) before failing. It was interesting to see the exact failure mode of the link after the tensile test.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/linkfail.jpg" title="failure" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The link after failure. This is cool because it is a textbook example of shear tearout. 
</div>

A lot more work went into this design than I am able to document here but I am grateful for the design experience it gave me and my team. It was fun to apply what we learned in class in a setting with real stakes, showing the usefulness of the material.