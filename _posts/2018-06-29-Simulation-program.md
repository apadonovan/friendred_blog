---
layout: post
title: "simulation Program"
description: ""
date: 2018-06-29
tags: laser, simulation
comments: true
---

<font size="2">
for the next step if I want to make a specific pattern, I can try to make all the lasrts point to a specific location (this could be used as a part of the performance, for example all the laser point folloing up the daners torso position). I could also try to make a more complex pattern out of ot as long as I have the way to make a single point tilt and pan to a specifi clocation. so I could maybe use noise function to manipulate it. Also, you can make them swap the position since they had a sibsific shape, like cross, like square. that would be crazy
</font>


<div style="padding:56.25% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/278519822?title=0&byline=0&portrait=0" style="position:absolute;top:0;left:0;width:100%;height:100%;" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>

<font size="2">
10th, July 2018 optimisation of the simulation program, there are 5 "laserStages" of this programm I designed. I also printed out the time and frame rates for debugging purpose. The challenge in here was the gap between each laser animation as most of them are mathematically calculated by sine wave or cosine function, so it will be hard to make the laser running smoothly without breaking the animation. so I add a gap animation between each transformation in order to make them transform consistently. The fact is, I found out actually it is a bit cumbersome to make the transaction animation as micro servo will move from one position to the next whenever I send a value from Open framworks, so it will fill in the gap by itself. This is something I didn't anticipate before. 
</font>

<div style="padding:74.53% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/279363354?title=0&byline=0&portrait=0" style="position:absolute;top:0;left:0;width:100%;height:100%;" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>
