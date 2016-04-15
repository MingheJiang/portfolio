---
layout: project
title: Baxter drawing
date: March, 2016
image: ![Alt text](/_projects/baxterdrawing.jpg)
---

## Overview
### Introduction:


The purpose of this project was to create a demonstration that combined robot arm kinematics and control with basic image processing. In the demo, a user draws a picture on a whiteboard and we use the right hand camera of a Baxter Research Robot to take an image of the user's picture. Canny edge detection is used to build a set of SE(3) waypoints that represent the user's picture. Finally, we solve the inverse kinematics for each waypoint, and design a joint space trajectory for Baxter's left arm to follow. Baxter then draws a replica of the user's original picture.



### Files In Package:
* #### In Package (drawing_left):
	
	>####[takephoto_right.py](https://github.com/MingheJiang/baxter_drawing/blob/master/takephoto_right/takephoto_right.py)
	
	>>This file firstly let the right camera find the content in the paper. Then after taking picture of the content and appling image processing on it, its pixels converted into x,y locations in Baxter workspace finally.
	
	>####[setup.dat](https://github.com/MingheJiang/baxter_drawing/blob/master/drawing_left/setup.dat)
	>>Setup right arm and distance.
	
* #### In Package (drawing_left):

	>####[joint_trajectory_action_server.py](https://github.com/MingheJiang/baxter_drawing/blob/master/drawing_left/joint_trajectory_action_server.py)
	
	>####[joint_trajectory_client.py](https://github.com/MingheJiang/baxter_drawing/blob/master/drawing_left/joint_trajectory_client.py)
	
	>>This file reads x,y,z data from the csv file which exported from takephoto_right.py and converts these locations into baxter 7 joint angles by using `baxter_ik_move()`. Then these sets of 7 joint angles are put into joint trajectory one by one. The trajectory is a function of time. Baxter will follow this trajectory to draw the content of picture. 
	
	>####[setup.dat](https://github.com/MingheJiang/baxter_drawing/blob/master/takephoto_right/setup.dat)
	>>Setup left arm and distance.

### Image Processing:

The right camera firstly gets the canny image of its vision by `cv2.Canny()` and then finds the location of the content in paper by finding and moving to the x,y location of the center of its contour rectangle several times with `cv2.findContours()` and `cv2.rectangle()`.

After finding the content and taking the canny image of it, the image is dilated and eroded in order to get the better result for houghing lines. By implementing `cv2.HoughLinesP()`, the sets of x,y pixels of these lines is obtained. 

Then the new x,y locations are splined by the function  `interpolate.splev()` to get much smoother lines. 

