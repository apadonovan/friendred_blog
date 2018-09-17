---
layout: post
title: "Stepper motor programme"
description: ""
date: 2018-06-29
tags: C, stepper motor
comments: true
---

<font size="3">

</font>


## Motors unipolar and bipolar:

<font size="2">
**bilopar:** each lead taken seperatly, Bi directional current flow through entire winding at a time unipolar: a Center tap added between the two leads, unidirectional flow in each 1/2 of winding, center tap connected to the ground or voltage source Motor driver needs 12V (actually is 5V - 30V) driver supply; 200 full steps (1600 microsteops) per evolution, 360/200=1.8, one step is 1.8 degree bipolar motor will generate more torque than unipolar, futhermore, unimotor need more wire, this will cause increase the parolause, winding increading temp, or you connetct bipolar configuration to unipolar ideally you can put 59 motors on the prototype

I connetced three stepper motors with three motor drivers by 12V 30A universal regulated switching power supply.
</font>

```C
  pinMode(8, OUTPUT);//direction control pinMode(9, OUTPUT);//step control
```

SM1-SM2

<font size="2">
Microstep Select Resolution Truth Table To enable the motor to step in 1/8th microsteps, we must set MS1, and MS2 HIGH. | MS1	| MS2	| Microstep Resolution | | L	| L	| Full Step (2 Phase) | | H	| L	| Half Step | | L	| H	| Quarter Step | | H	| H	| Eigth Step |

```C
digitalWrite(dir, LOW); //Pull direction pin low to move "forward"
digitalWrite(MS1, HIGH); //Pull MS1, and MS2 high to set logic to 1/8th microstep resolution
digitalWrite(MS2, HIGH); for(x= 1; x<1000; x++) //Loop the forward stepping enough times for motion to be visible {
digitalWrite(stp,HIGH); //Trigger one step forward delay(1);
digitalWrite(stp,LOW); //Pull step pin low so it can be triggered again delay(1); }
```

If I put delay(1), the compete pause will be 2ms per time, since 1000ms per second, so 1000/2=500ms per second
</font>

<div style="padding:56.25% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/277082161?title=0&byline=0&portrait=0" style="position:absolute;top:0;left:0;width:100%;height:100%;" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>
