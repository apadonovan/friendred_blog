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

<img src="/friendred_blog/assets/images/draft.jpg">

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

<iframe src="https://player.vimeo.com/video/277084253" width="640" height="360" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>
<p><a href="https://vimeo.com/277084253">IMG_8023</a> from <a href="https://vimeo.com/user41998022">Friendred</a> on <a href="https://vimeo.com">Vimeo</a>.</p>


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

for the laser control, two elements that I needed to bare in mind is that shift register and laser base.
for the base design, fistly I downloaded a model from thingnivers and designed a laser holder from.
<img src="/friendred_blog/assets/images/laser_holder.png">
<img src="/friendred_blog/assets/images/top_view_lasers.png">

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

<iframe src="https://player.vimeo.com/video/278129503" width="640" height="360" frameborder="0" allowfullscreen></iframe>

##Motors
unipolar and bipolar:
<font size="2">
bilopar: each lead taken seperatly, Bi directional current flow through entire winding at a time
unipolar: a Center tap added between the two leads, unidirectional flow in each 1/2 of winding, center tap connected to the ground or voltage source
Motor driver needs 12V (actually is 5V - 30V) driver supply; 200 full steps (1600 microsteops) per evolution, 360/200=1.8, one step is 1.8 degree
bipolar motor will generate more touque than unipolar, futhermore, unimotor need more wire, this will cause increse the parolause, winding increading temp, or you connetct bipolar configuration to unipolar

ideally you can put 59 motors on the prototype, I have got 40 lasers
<>img src="/friendred_blog/assets/images/top_view_lasers.png"

I connetced there stepper motors with three motor drivers. powerered by 12V 30A universal regulated switing power supply
</font>
<font size="2">
```java
pinMode(8, OUTPUT);//direction control
pinMode(9, OUTPUT);//step control
```
</font>
SM1-SM2
<font size="2">
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
</font>

<font size="2">
If you put delay(1), the compete pause will be 2ms per time, since 1000ms per second, so 1000/2=500ms per second
</font>

##software

<font size="2">
skeleton on the mac, torso position in the 3D space.

</font>

##fabrication of the metal
<font size="2">
Fabricating metals, for now,  I fabricated the metal tructure consisted of two rings as well as the conjuctions of the rings, and top circle made by metal. via rolling machine, cutting, grinding, Plasma arc welding (PAW).
1. The next step is considering how to drill the whole of top and bottom to fix the MDF or acrylic board. The solution is using 16 mils self drilling / contour sunk screw, it doesn't work with 9mm, but it works with 6mm MDF board via testing
2. how to fix the motor holder on the side of the rings
3. how to find a way to connetc 18+ lasers holder onto the two rings without damage it
4. the conection between the nylon thread and motor spinning pin, I therefore used pulley to connect pin and thread (could be fine cored/ nylon, fish wire)
5. you might also need some wholes for the wires get out of the structure
6. polish and painting to avoid rust(for the polish I used grinder with different sharperness of the plan). The external circles comparally are easier to polish and grind, as the three different parts of the structure are different metal materials. However the cental disk is quite hard to grind, I guess I have to spay it by metallic paint.
7. In the endm due to a the difficuilties of the grinding, so I have to just spay it (smooth silver direct onto metal), the metal part was good, however the MDF part in order to retrive a smooth surface, thsu I had to sparay multiple times, still not sure about the the result
</font>
what's the next step!!!!
19th June--spend an day to drill the MDF and arcrylic board onto the structure, for the arcrylic, the frangibility of the material, so I had to drill a whole first, then use self drilling screws go through it.

<img src="/friendred_blog/assets/images/metal_1.JPG">

<img src="/friendred_blog/assets/images/metal_2.JPG">


##Wearable
<img src="/friendred_blog/assets/images/mask.png">
<img src="/friendred_blog/assets/images/mask_2.png">

the face maks are for two different performers, the mask ideally would be made out of matel structure and using the two day/see through mirror arcylic board, thus when performers are wearing it, the other side can reflects the lights, the side close to performer can see through
<img src="/friendred_blog/assets/images/face_mask_f.jpg">
