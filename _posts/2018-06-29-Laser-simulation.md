---
layout: post
title: "laser simulation"
description: ""
date: 2018-06-29
tags: laser, simulation
comments: true
---

29th of June, the gole was trying to sorve the problem of conecting lasers to the laptop, Thanks to Roy, I could use the xBee (with XBee shield and XBee adaptor) to replace the wifi module, I haven't tried it yet, but will try it as soon as I received the conponenets. also with Roy's help, I could simulate the lasers, for now I managed to make a nice movement by

```C++
lasers[i].setPanTilt(pan, tilt);//this is the basic line of the test
lasers[i].setPanTilt(sin(ofDegToRad(ofGetElapsedTimef()*10))*360*i/lasers.size(), tilt*i/lasers.size());
```
the next step is to make a system of how I decide the aesthetics of lasers movements following up the perormer
and even with XBee wifi module, I still have to find a way to deconstruct and reconstruct the data from openframework to arduino, but bare that in mind, you will have 40 lasers -- 80 servermotors -- each modeule will have three pins, which means you will need a microcontroller have 40*3=120 pinouts, so for now I have a MEGA, then 53 pins, so maybe I need another two MEGA?

<img src="/friendred_blog/assets/images/laser_simulation.png">
<iframe src="https://player.vimeo.com/video/277711455" width="640" height="380" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>
<p><a href="https://vimeo.com/277711455">laser_simulation</a> from <a href="https://vimeo.com/user41998022">Friendred</a> on <a href="https://vimeo.com">Vimeo</a>.</p>

for the working progree show, I will present the demosntration of how these 6 motors work in a sequence and get the data from openframwork via XBee and shield. Here is a monumental video for the first 6 haha

5th of July, I had a problem with making animation of the lasers (6 for now), the probelme was I had to put the data which used to transfer to the motor in somewhere else, then I can control the simulation by slider, yet still could not control it if I have any animation. Thanks Lior, the problem was I need to have roughly a second (60 fram) gap in order to awake servo lib for some reasons, but I spend a whole evening and a whole morning stucked in this.

<iframe src="https://player.vimeo.com/video/278129503" width="640" height="360" frameborder="0" allowfullscreen></iframe>

for the next step if I want to make a specific pattern, I can try to make all the lasrts point to a specific location (this could be used as a part of the performance, for example all the laser point folloing up the daners torso position). I could also try to make a more complex pattern out of ot as long as I have the way to make a single point tilt and pan to a specifi clocation. so I could maybe use noise function to manipulate it. Also, you can make them swap the position since they had a sibsific shape, like cross, like square. that would be crazy


<img src="/friendred_blog/assets/images/Laser_simulation2.png">


<iframe src="https://player.vimeo.com/video/278519822" width="640" height="360" frameborder="0" allowfullscreen></iframe>

<img src="/friendred_blog/assets/images/laser_army.JPG">

<img src="/friendred_blog/assets/images/wire_army.JPG">

<img src="/friendred_blog/assets/images/lable_wire.JPG">
<img src="/friendred_blog/assets/images/fundation_L.JPG">
<img src="/friendred_blog/assets/images/drill_whoel_f.JPG">
<img src="/friendred_blog/assets/images/crimple.JPG.png">
