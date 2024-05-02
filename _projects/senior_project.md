---
layout: page
title: Senior Project
description: Path of Lights and Sounds
img: assets/img/paththumb.jpg
importance: 1
category: school
related_publications: true
---

For my senior project, me and a group of 4 others had to make a step activated, light-up, musical path for the Girl Scouts of California's Central Coast. They wanted a path of 25 tiles to be able to play "Jingle Bells" at their winter wonderland event. This was a really fun project to work on and a great learning opportunity. For full official reports of the project, check <a href="https://digitalcommons.calpoly.edu/mesp/742/">here</a>. For a brief synopsis of the project and what I did on it, continue on!

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/path1.jpg" title="completed path" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Here's what the finished path looked like!
</div>

<p align="center">
    <iframe width="315" height="560" src="https://www.youtube.com/embed/u1-BN-DRcQI" frameborder="0" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</p>
<div class="caption">
    And here's it in action!
</div>

This was truly a lesson in product design as my group quickly found out. Throughout ideation and prototyping, we constantly had to make our engineering design decisions with user perception, behavior, and safety in mind. We used functional decomposition and quality function deployment to make sure we were on the right track with our prototypes. We considered the design's failure modes, manufacturability, assembly, sourcing, and risks to make sure nothing could go wrong.

The full team collaborated on the structural design of the tile because if the tile physically broke, the project would be deemed a hazard and complete failure. We sized them in order to support a 300lb adult jumping on the tiles. We also had cost in mind as our budget wasn't huge, and we tried to use budget materials such as aluminum and recycled plastics in large quantities to save money. The trapezoidal shape of the tiles was in order to make the path curve with only one unique tile shape. A single tile was about 1.5ft wide by 2.5ft long.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/pathjump.jpg" title="tile in use" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    A single finished tile (foot for scale).
</div>

As a full team, it took us around 300 hours to fully make all of the tiles requested for the event. It was a test of our team's resolve and definitely taught us a lesson in using the right tools for the job. Using the second best method for a process doesn't sound too bad until you have to do it 240 times. It also gave us an appreciation for what Cal Poly's machine shops provide for free as students.

I headed the electronics design of the tile with another teammate and sourced all electronic components. I fully designed the PCBs used in every tile after iterating through two test versions and updating with my teammates feedback. When ready, we assembled all 30 PCBs ourselves. This was tedious but we prevailed in the end with 30 PCBs running off of Raspberry Pi Picos.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/path30PCB.jpg" title="All 30 PCBs" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/pathPCB.jpg" title="Single PCB" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    On the left you can see all the PCBs we made fully finished in their enclosures! On the right is a single PCB before being wired up.
</div>

I did all the coding by myself and had to troubleshoot many small issues. I coded in Circuit Python as it seemed like the most user friendly language to hand off to a non-technical group afterwards. It is very introductory and has a lot of documentation online for help. It was also nice that the Pico appears as a file system when plugged into a computer.

The tiles ran off a finite state machine that loaded presets from the last time the tile was used. If the first tile was stepped on during power up, it would send out song information that all other tiles would use and relay down the line. This means that if you need to update the song information, you only had to do so on the first tile. 

I also created a graphical user interface (GUI) to aid in the reprogramming of the tiles for a different song. This also invovled sourcing sound files for a full piano range to be as general as possible in future usage. After going through all of the GUI's prompts, a text file would be created that then gets dropped onto the first tile's file system.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/pathgui.jpg" title="GUI" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The GUI that helps the user reprogram the tiles for a new song.
</div>

I also headed testing for the tiles. It was difficult to write concrete engineering tests to be done on this product. I settled on writing tests to verify that the tile meets the needs it set out to. Most of these were covered by a user test group that covered most subjective attributes regarding the tiles. The others were engineered to simulate using the tile, such as an side-impact test with a weighted bucket, a slip test for measuring the traction, and more. The only test that we didn't do that we likely should've would be to take one tile to failure and see what it takes to break it, but due to time and materials we were not able to.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/pathtest.jpg" title="Testing the tile" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The tile being tested by using a swinging bucket for a repeatable side-impact, measuring how much the tile displaced upon repeated impact when staked to the ground.
</div>

This project was most valuable to me as experience in leading a group and working within the requests of a non-technical customer for a diverse user group. There were a lot of issues that needed to be fixed and needs that had to be met, and in the end my group was very successful in its efforts. 