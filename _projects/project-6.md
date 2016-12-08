---
layout: project
title: Android Line Follower Mobile Robot
date: May 1, 2016
image: ALFMR_1.jpg
image2: ALFMR_2.png
image3: ALFMR_3.png
image4: ALFMR_4.jpg
image4: ALFMR_4.jpg
image5: ALFMR_5.jpg
image6: ALFMR_6.png
---

## Overview

This project was part of the course Advanced Mechatronics, at Northwestern University. The goal of this project was to design, fabricate, and program a robotic cart made of laser cut and 3D printed parts and then let it automatically follow the colored line in the ground with PIC32 and USB CDC.

The PCB schematic shown in the image below was used:
<p align="center">
<img src="{{site.baseurl}}/{{site.image_path}}/{{ page.image2 }}" width="600" height="350" />
</p>

Wheels were designed via CAD and 3D printed:
<p align="center">
<img src="{{site.baseurl}}/{{site.image_path}}/{{ page.image3 }}" width="250" height="250"  />
<img src="{{site.baseurl}}/{{site.image_path}}/{{ page.image4 }}" width="290" height="250" />
</p>

Cart were designed via Solidworks and made of laser cut:
<p align="center">
<img src="{{site.baseurl}}/{{site.image_path}}/{{ page.image5 }}" width="400" height="250" />
</p>
One sliders in the Android app was used to control the threshold of camera. There were 3 points on the phone screen which represented the center of mass. 

The default was set to be 100% PWM output for both left and right motors. PWM of motors was changed in order to change direction. When the COM2 was larger than 320, the 
PWM of the right motor was decreased by (COM3-320)/320. When the COM2 was smaller than 320, the PWM of the left motor was decreased by (320-COM3)/320.

<p align="center">
<img src="{{site.baseurl}}/{{site.image_path}}/{{ page.image6 }}" width="250" height="350" />
</p>



All of the code for this project is hosted on this page:
[Github page](https://github.com/MingheJiang/MingheJiang_ME433_2016/tree/master/HW16)


<p align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/YmRv4T1eEao" frameborder="0" allowfullscreen></iframe>
