---
layout: page
title: hungry hippo bot
description: ping pong ball collector
img: assets/img/hippothumb.jpg
importance: 2
category: school
---

In my Mechanical Control System Design course, we were tasked with designing a PCB and robot to be able to roam around an arena and collect a specific color of ping pong balls. Working with a partner, we split up and separately took on the mechanical and electronics design. He handled the design, structure, and assembly of the robot while I focused on PCB design, wire harnessing, and sensor/actuator selection and usage.

Due to time constraints in the quarter system, none of the class completely finished the project. Me and my partner were able to complete the robot but did not get to designing the algorithm of how it should navigate around the arena to look for ping pong balls.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/hippothumb.jpg" title="robot finished" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The completed robot. Drove on two drive wheels and a follower wheel in the back.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/hippofront.jpg" title="robot finished" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Taking a closer look, you can see two intake wheels to feed ping pong balls into the robot's chute. Once inside, there's a color sensor to determine if the ball is the right color and a limit switch to see if the chute is full.
</div>

This was my first experience with PCB design and it took some time to get up to speed with using Autodesk's PCB designer. Once learned though, designing the PCB wasn't too bad and taught me a lot about designing electronic systems, reading data sheets, and planning for compatibility. 

Key features of the PCB were:
    ---
    • ran using STM32F411CEU6 microcontrol unit
    • 12V to 5V switching regulator
    • 5V to 3.3V linear voltage regulator
    • 5V relay (for motor power)
    • 4 DRV8251 H-Bridges for motor driving
    • reset button
    • 25 MHz crystal oscillator
    • reverse polarity protection for 12V battery connection
    ---

<div class="row justify-content-sm-center">
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/hippopcbbare.jpg" title="pcb bare" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/hippopcbassembled.jpg" title="pcb assembled" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The PCB I designed! On the left you can see it before assembly and on the right is it ready for action.
</div>

I believe I made two mistakes in the PCB design. The first was that reset pin needed to be grounded to properly use the debugger so we hotwired this connection. The other was that the NMOSFET activating the relay had too high of a resistance to get above the threshold voltage. We were lucky enough to have a spare on hand that had a lower internal resistance to properly activate the relay.

The PCB was designed to be used with:
    ---
    • 2 line followers
    • 1 color/proximity sensor
    • 3 motors (2 with encoders)
    • 1 IMU for heading
    • 1 limit switch
    • 1 SPI connection (unused)
    ---

The unused SPI connection was swapped to an I2C connection for interfacing with an nrf24L01+ for our robot's deadman switch. This was connected to a joystick and the robot would only drive when the joystick was pressed. There was also a manual control mode where the robot operated like a regular RC car.

I wrote code in C for interfacing with all these sensors and actuators and got them all to work. I wish we had time to fully develop the code to autonomously drive around the arena.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/hippowire.jpg" title="robot backside" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The wire harness. You can also see the limit switch and follower wheel better from this angle.
</div>

I'm not proud of the wire harness but considering it was my first time fully designing these connections and making quick fixes, I think it was adequate for the robot.

Overall, I am proud of this project and everything it taught me. With more time, I am confident we could have gotten it working for the competition. I think it is very telling that we did a good job on this considering most people in the class did not get to full robot integration by the end of the quarter.