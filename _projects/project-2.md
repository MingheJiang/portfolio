---
layout: project
title: Baxter Pick and Place
date: December 10, 2015
image: baxterpickandplace.png
---

## Overview

This project was the final project of the course ME 495, Embedded Systems in Robotics, at Northwestern University. The main goal of it was letting the Baxter robot autonomously pick objects off of a work surface and place them in a container. The blocks could be in different shapes, colors and placed at any position and orientation on the table.

### Capabilities:

* Multiple Object Shapes
* Multiple Object Sizes
* Multiple Object Colors
* Multiple Object Orientations
* Dynamic Image Processing - can adjust object positions/orientations between picks

The whole task could be splited into two parts: **Image Processing** and **Inverse Kinematics**.

### Image Processing:

The balls and squares were found by using colour filtering image processing from the
OpenCV library. Defaults were set to look for green and red filters in the
Hue Saturation Value colour spectrum. The two filtered images were added together
using an even weighting. 

A minimum enclosing rectangle was drawn around the biggest found contour. The two 
corners with the minimum y-value were used to find a slope and thus the
orientation of the object that needed to be picked up. 

#### Cameras:
The camera attached to the right hand of Baxter was used to do the image
processing. First it was orientated at a known fixed position to scout for objects.
Once the biggest object was found, it re-orientated itself above the object. Then the number of iterations was adjusted that Baxter used to recheck its position above
the object. Once the object was found, Baxter's camera calculated the slope and reorientates itself to pick the object. 

### Inverse Kinematics:

The  `ik_solve() ` called an `Inverse-Kinematics(IK)` service provided by the ROS node  `/ExternalTools/<limb>/PositionKinematicsNode/ `

It took three elements: limb, desired Quartesian coordinate and orientation of the end effector of the Baxter and returned seven joint angles that would get the arm to that position. 

Refering to Inverse Kinematics Solver Service on the Baxter API reference page:
<http://sdk.rethinkrobotics.com/wiki/API_Reference#arm-joints>

The  `seed_mode ` was always set to 1 to use the user defined seeds as the initial joint angles guess for ik. The  `seed_angels ` were all very close to the current joint angles that must be in the Baxter's workplace. Since it was normally hard to get ik converge to a solution, random noise had been generated and added to the current joint angles. A list of seed angles could thus be implemented to try for at most 20 times to solve the inverse kinematics, which should be robust enough to find a valid solution. 


All of the code for this project is hosted on this page:
[Github page](https://github.com/therrma2/Baxter-Pick-And-Place)


<p align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/Uo60e5Leo50" frameborder="0" allowfullscreen></iframe>
