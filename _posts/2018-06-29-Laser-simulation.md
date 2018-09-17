---
layout: post
title: "laser simulation"
description: ""
date: 2018-06-29
tags: laser, simulation
comments: true
---

<font size="3">
29th of June, the goal was trying to solve the problem of connecting lasers with open frameworks, one of the options is using the XBee (with XBee shield and XBee adaptor). Another option is using photon wifi module. I haven't tried them both yet. but I will run some tests as soon as I received the components.
</font>


###### some code in Open Frameworks in order to sync the pan and tilt value to the micro servo motor

```C++
lasers[i].setPanTilt(pan, tilt);//this is the basic line of the test
lasers[i].setPanTilt(sin(ofDegToRad(ofGetElapsedTimef()*10))*360*i/lasers.size(), tilt*i/lasers.size());
```

<font size="3">
The next step is to make a system of how I decide the aesthetics of lasers movements following up the performers
and even with XBee wifi module, I still have to find a way to deconstruct and reconstruct the data from Open Frameworks to Arduino. This is a technical challenge as I will have to communicate with 40 lasers, 80 server motors, two stepper motors and three LED lights strips witch has 600 pixels on it. Each laser module will have three pins, which means I will need a micro controller have 40*3=120 pinouts, so for now I have a MEGA, then 53 pins, so maybe I need another two MEGA? That was the question I asking myself, but lucky enough I changed plan in the end, I used servo drivers instead of connecting each servo to the pinout directly.
</font>

<div style="padding:59.36% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/277711455?title=0&byline=0&portrait=0" style="position:absolute;top:0;left:0;width:100%;height:100%;" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>

<font size="2">
For the work in progress show, I will demonstrate how 12 motors work in a sequence and get the data from OF via XBee and XBee shield. Here is a monumental video for the first 12 motors.
</font>

<font size="2">
5th of July, I had a problem with making animation of the lasers (6 for now), the probelme was I had to put the data which used to transfer to the motor in somewhere else, then I can control the simulation by slider, yet still could not control it if I have any animation. Thanks Lior, the problem was I need to have roughly a second (60 fram) gap in order to awake servo lib for some reasons, but I spend a whole evening and a whole morning stucked in this.
</font>

<iframe src="https://player.vimeo.com/video/278129503" width="640" height="360" frameborder="0" allowfullscreen></iframe>
