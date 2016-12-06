---
layout: project
title: Block Rolling Downwards the Stair
date: December 1, 2015
image: blockdown.png
---

## Overview

This project was the final project of the course ME 314, Machine Dynamics, at Northwestern University. It was about simulating the process of a rectangular rolling downwards the stairs by using [Wolfram Mathematica](https://www.wolfram.com/mathematica/).

The process can be splited into three parts:  

* At first, there were two rectangles with the same mass (m = 1) and shape on the second floor. Initialized with a velocity of 2m/s, the first mass would move forward and hit the right mass. 

* After the impact, both masses would change their motions. According to
the 'Law of Momentum Conservation', the motion of two masses would satisfy
the following equation during the impact: m1v1 = m2v2

* After the collision, the left rectangle would move backward and the right one
would gain some speed and move forward. The right mass would then reach the
end of the second floor and follow a parabolic trajectory as it is dropping.
Mathematica function `WhenEvent` was used to obtain the time when the right mass hit the first stair as well as the point where the impact happens. 

Numerical method was used to solve the velocity of the mass after the impact.

<p align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/ly_A5m0RMMk" frameborder="0" allowfullscreen></iframe>
