---
layout: project
title: Robotic Cart
date: May 1, 2015
image: advanced.jpg
---

## Overview

This project was part of the course ME 433, Advanced Mechatronics, at Northwestern University. The goal of this project was to build a robotic cart which could automatically follow the red line in the ground with PIC32 and Android CDC.

One sliders in the Android app was used to control the threshold of camera. There were 3 points on the phone screen which represented the center of mass. 

The default was set to be 100% PWM output for both left and right motors. PWM of motors was changed in order to change direction. When the COM2 was larger than 320, the 
PWM of the right motor was decreased by (COM3-320)/320. When the COM2 was smaller than 320, the PWM of the left motor was decreased by (320-COM3)/320.

All of the code for this project is hosted on this page:
[Github page](https://github.com/MingheJiang/MingheJiang_ME433_2016/tree/master/HW16)


<p align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/YmRv4T1eEao" frameborder="0" allowfullscreen></iframe>
