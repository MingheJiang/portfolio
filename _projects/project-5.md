---
layout: project
title: SmartErasor
date: March 10, 2016
image: smart.png
---

## Overview

This project was the final project of the course EECS 332, Intro. to Computer Vision, at Northwestern University. The goal of this project was erasing a row of characters automatically and gradually while letting the background texture be unchanged.

## Steps

* Find red region and get its average HSV value.
* Filter the image and get red areas in HSV space.
* Filter the pen’s tip and Get the minimum rectangle which can hold the pen’s tip.
* Kalman filter is added to estimate the pen tip position.
<p align="center">
<img src="https://s3.amazonaws.com/f.cl.ly/items/0f3c1p3z082G2m031o0f/smart3.png?v=13b9f977" width="580" />


<p align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/aJ_qrJvRTvI" frameborder="0" allowfullscreen></iframe>
