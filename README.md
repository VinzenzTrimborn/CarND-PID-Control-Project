# CarND-Controls-PID
Self-Driving Car Engineer Nanodegree Program

## Introduction

In this project I implemented a PID controller  to stier a car around a given track in the simulator. The simulator provides the cross check error and the velocity which is needed to compute the steering angle. 

## Discription of the effects of each P, I, D component

I modified the three parameters Kp, Ki and Kd by hand until I got a satisfying result. I started of with fairly good valiues given by Sebastian during the previous lessons. 

#### How do these parameter affect our system and our final outcome:

- Kp equals a proportional factor to the cross track error. If we only use this parameter and set the othes to 0 the car would always overshoot. A high value results in a large change in the output of our PID controller. If the value is too high the system is unstable and the car would always oscillate but never stay in the middle of the lane. However, when Kp is too small and the error is large the PID conroller would not be sensitive enought to this large error. 

- Ki is the integral gain and is multiplied by the accumulated error. SInce the accumulated error becomes larger over time it will eventually correct the steering angle. However, if Ki is large it can cause the present value to overshoot the goal, since the integral terms is the sum of errors in the past.

- Kd is the derivative gain and is multiplied by the the derivative of the error. When the error gets smaller the derivative of the error gets smaller too and the car does not overshoot. If Kd is too large the PID controller steers back again too quickly befor it reaches the target. When it is too small it steers up again to late and could overshoot.