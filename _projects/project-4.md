---
layout: project
title: Block rolling downwards the stair
date: December 1, 2015
image: blockdown.png
---

## Overview

This project was the final project of the course ME 314, Machine Dynamics, at Northwestern University. This project was about simulating the process of a rectangular rolling downwards the stairs by using [Wolfram Mathematica](https://www.wolfram.com/mathematica/).

The process can be splited into three parts:  

At first,There were two rectangles with the same mass (m = 1) and shape on the second floor.Initialized with a velocity of 2m/s, the first mass will move forward and hit
the right mass. 

After the impact, both masses will change their motions. According to
the 'Law of Momentum Conservation', the motion of two masses will satisfy
the following equation during the impact: m1v1 = m2v2

After the collision, the left rectangle will move backward and the right one
will gain some speed and move forward. The right mass will then reach the
end of the second floor and follow a parabolic trajectory as it is dropping.
Mathematica function `WhenEvent` is used to obtain the time when the right mass hit the first stair as well as the point where the impact happens. 
Numerical method is used to solve the velocity of the mass after the impact.

<p align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/ly_A5m0RMMk" frameborder="0" allowfullscreen></iframe>
