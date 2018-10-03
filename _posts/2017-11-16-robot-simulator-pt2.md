---
layout: post
title: Robot Simulator Part 2 - CCD
tags:
- inverse kinematics
- Scara robot
- AngularJS
- Cyclic Coordinate Descent

---

I started experimenting with the Cyclic Coordinate Descent algorithm. CCD is an iterative approach to inverse kinematics that works like this:

- Repeat the following until the robot endpoint is within a tolerable distance of the goal:
	- Repeat the following for each joint in order, starting from the end-most joint:
		- Using basic trig, find the angle of rotation of that joint that minimizes the distance from the robot endpoint to the goal. *To visualize, draw a line from the joint to the goal, then rotate that joint until the endpoint lies on the line*

When I first ran the simulator, I accidentally had the code starting from the first joint rather than the last. The algorithm still worked, but the first joints appeared to overshoot by quite a bit.

![](/assets/img/2017-11-16/2.png)

When I switched it to the correct order, it appeared that all the joints overshoot by quite a bit.

![](/assets/img/2017-11-16/1.png)

I decided to try limiting how much each joint could move during each iteration to 1°. I thought this would give a more visually pleasing solution but take a little longer. The output was nicer looking, and in most cases the algorithm actually ran much faster.

![](/assets/img/2017-11-16/3.png)


Right now, the simulator just jumps to the point when you click. I would like to animate it so I can see what each step actually looks like. I also have a few other ideas for some advanced optimization that I'm hoping to try soon.