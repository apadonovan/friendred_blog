movement---
layout: post
title: "Moqiu performance"
description: "working progress"
date: 2018-06-04
tags: test, style
comments: true
---

--

-----

##Conception:
<font size="2">

The symbolic relationship between **culture** and **technology** has always been interesting to me. I will describe how I plan to build on the unorthodox conversation between ethnographic convention and technology, via the analysis and interpretation of information into visuals and sound, allowing audiences to effectively experience the information. Moreover, I will explore the minimalism, futurism and materiality existing in interactive experiences and processes, by using various methodologies from different perspectives and domains.

I will combine Hmong society and rituals into a body commanding performance. Through researching the mythology, rituals, healing ceremonies and different modalities of arts in the Hmong tribe,. my aim is to create an audio based, interactive performance.

The Hmong religion is traditionally animist. In traditional Hmong practice, **all animate and inanimate matter possesses life.** The aim of this performance is to use unusual digital techniques to restore, deconstruct and reconstruct the manifesto of the ritual being represented by technology. Different cultures and religions have their own mythologies and rituals. Several topics will be covered, for example, ‘Moqiu’ (Fig.1), a ritual which Hmong people celebrate in May of the Lunar calendar to memorize the myth in which ‘Moqiu’ was built to communicate with the sun by ancestors to stop them suffering from catastrophe and pestilence.
</font>

<img src="/friendred_blog/assets/images/moqiu.jpg" alt="Girl in a jacket" width="300">
<img src="/friendred_blog/assets/images/moqiu2.jpg" alt="Girl in a jacket" width="300">

<font size="2">
In a different cultural context, animism, which encompasses the beliefs that all material phenomenon has agency, can be presented by a different people in a different way. In the Hmong community as well as in other cultures such as Yi, Hani, Zhuang and etc. In this ritual, people will lean their waist on the side of the beam. Performers spin and jump using their tiptoes. This swing-like ritual behaviour was used to symbolise the anticipation of Hmong to contact the deities.  Before the spiritual practice, a priest will produce the worship ceremony. Traditionally, they sprinkle liquor up, down, left and right, a this is necessary to revere and honour the sky, soil, ancestors and deities for guidance and protection. Pork will be piled in the intersection of two beams to intensify grating for gaining welfare and health of the living.
</font>

<font size="2">
The human body and technology extend the way how people perceive culture and ideology during performance. My aim is to combine these two parts of the world, ritual and technology to create a new-age ritual. In this project, the Moqiu is part of the core ritual from the Hmong culture symbolising the worship, therefore I extracted the attributes of the balance out of bean and demonstrate in my concept design (picture below).  
</font>

<img src="/friendred_blog/assets/images/scene_2_2.jpg">

-----
##Fabrication:
###Circle structure
<font size="2">
This piece ideally should be hanging on the ceiling, the stepper motor (Fig.5) on the top would control the ‘circle’ spin horizontally and the other two motors (Fig.2) on the side will be used to making the pipe (Fig.1) move vertically. The profile of the circle (Fig.3) is a ‘U’ shape, which LED strip can be put in the notch of the circle.
One of the biggest challenge is the fabrication of the installation, the material could be aluminium, plywood or acrylic. The idea material is aluminium, which economically more expansive than the plywood and technically harder to fabricate.
</font>
<img src="/friendred_blog/assets/images/joints_v12.png">
<img src="/friendred_blog/assets/images/joints_v13.png">
<img src="/friendred_blog/assets/images/joints_v14.png">
<img src="/friendred_blog/assets/images/joints_v15.png">

###Brainstorm
<img src="/friendred_blog/assets/images/ideas.png">


###tech diagram
<img src="/friendred_blog/assets/images/tech_diagram.png">

###prototype
<font size="2">
Before I officially start fabricating the installation and in order to make sure the size and appearance are close to the design I engeneered in the Fusion and Cinema4D, the best way to do is the prototype. I, hence, made a 1:1 ratio mockup made by cardboard (12 pieces) and sliced by Fusion Slicer.
</font>

<img src="/friendred_blog/assets/images/board2.png" width="220">
<img src="/friendred_blog/assets/images/board3.png" width="220">
<img src="/friendred_blog/assets/images/board4.png" width="220">

<img src="/friendred_blog/assets/images/card1.JPG" width="340">
<img src="/friendred_blog/assets/images/card2.JPG" width="340">

[//]: <> (<img src="/friendred_blog/assets/images/card3.JPG" width="340">)
[//]: <> (<img src="/friendred_blog/assets/images/card4.JPG" width="340">)

##Laser

<font size="2">
Another main part of the piece is a laser system mounted onto the circle installation and interactively controlled by performers, kinect will be used to detect the dancer's skeleton and trajectory of the movements and
</font>
[//]: <> (<img src="/friendred_blog/assets/images/laser_case.png" width="320">)

<img src="/friendred_blog/assets/images/scene_3_1.jpg">

<img src="/friendred_blog/assets/images/scene_4.jpg">

##Motors
unipolar and bipolar
bilopar: each lead taken seperatly, Bi directional current flow through entire winding at a time
unipolar: a Center tap added between the two leads, unidirectional flow in each 1/2 of winding, center tap connected to the ground or voltage source
Motor driver needs 12V (actually is 5V - 30V) driver supply; 200 full steps (1600 microsteops) per evolution, 360/200=1.8, one step is 1.8 degree
bipolar motor will generate more touque than unipolar, futhermore, unimotor need more wire, this will cause increse the parolause, winding increading temp, or you connetct bipolar configuration to unipolar

I connetced there stepper motors with three motor drivers. powerered by 12V 30A universal regulated switing power supply

```java
pinMode(8, OUTPUT);//direction control
pinMode(9, OUTPUT);//step control
```
SM1-SM2
Microstep Select Resolution Truth Table
To enable the motor to step in 1/8th microsteps, we must set MS1, and MS2 HIGH.
| MS1	| MS2	| Microstep Resolution |
| L	| L	| Full Step (2 Phase) |
| H	| L	| Half Step |
| L	| H	| Quarter Step |
| H	| H	| Eigth Step |
```java
digitalWrite(dir, LOW); //Pull direction pin low to move "forward"
digitalWrite(MS1, HIGH); //Pull MS1, and MS2 high to set logic to 1/8th microstep resolution
digitalWrite(MS2, HIGH);
for(x= 1; x<1000; x++)  //Loop the forward stepping enough times for motion to be visible
{
  digitalWrite(stp,HIGH); //Trigger one step forward
  delay(1);
  digitalWrite(stp,LOW); //Pull step pin low so it can be triggered again
  delay(1);
}
```

If you put delay(1), the compete pause will be 2ms per time, since 1000ms per second, so 1000/2=500ms per second

##software

<font size="2">
skeleton on the mac, torso position in the 3D space.


</font>

##software
Fabricating metals, for now,  I fabricated the metal tructure consisted of two rings as well as the conjuctions of the rings, and top circle made by metal. via rolling machine, cutting, grinding, Plasma arc welding (PAW).
1. The next step is considering how to drill the whole of top and bottom to fix the FDM or arcrylic board.
2. how to fix the motor holder on the side of the rings
3. how to find a way to connetc 18+ lasers holder onto the two rings without damage it
4. the conection between the nylon thread and motor spinning pin
5. you might also need some wholes for the wires get out of the structure
5. polish and painting to avoid rust  

<img src="/friendred_blog/assets/images/scene_4.jpg">
