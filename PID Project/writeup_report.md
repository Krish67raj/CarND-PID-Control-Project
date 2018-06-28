## Writeup Report

---

**PID Controller Project**


The goals / steps of this project are the following:

* Tune the PID controller hyperparameters.
* Test the result on the simulator. 
* Play around with the throttle.


## [Rubric](https://review.udacity.com/#!/rubrics/824/view) Points
### Here I will consider the rubric points individually and describe how I addressed each point in my implementation.  

---
### Writeup / README

#### 1. Provide a Writeup / README that includes all the rubric points and how you addressed each one.  You can submit your writeup as markdown or pdf.  [Here](https://github.com/udacity/CarND-Vehicle-Detection/blob/master/writeup_template.md) is a template writeup for this project you can use as a guide and a starting point.  

You're reading it!

### PID Controller

#### 1. Student describes the effect of the P, I, D component of the PID algorithm in their implementation.

The PID Control system is a very popular control system or controller which has a lot of applications in world. PID stands for Proportional, Differential and Integral control. The basic componenets of PID are explained below:
1. The Proportional Term:- This is the correction which is done proportional to the direct error which arises at each step in the system. The correction term is directly 				proportional to the cross track error(CTE) which is the deviation from the original set point trajectory of our system. The proportional constant 				(Kp) is multiplied with the CTE do the correctrion.	

2. The Differential Term:- This is the correction which is done in order to achieve the steady state faster. The correction is proportional to the differnce in the 				current CTE and the previous CTE. The differential gain(Kd) or constant is multiplied with the difference to do the correction.

3. The Integral Term:- This is the correction which is done in order to reduce the steady state error of the system. The correction is therefore proportional to the 				steady state error of the system. We accuymulate the errors from  our 1st step to current step and do coorection proportional to this error. The 				Integral constant(Ki) is multiplied with the accumulated error for the correction.

In this project, I started with the values as givel in the PID implementation of the Udacity classroom which are Kp = 0.2, Kd = 3.0, Ki = 0.004. I then tweaked these parameters manually by hit and trial and, finally I reached to the current values I have used. Kp = 0.13, Kd = 3.5, Ki = 0.00012. The car is able to run pretty good and completes a lap without much deviation from the center. However, there a little bit of fluctuations at sharp turns, but the car remains on track.

### Discussion

#### 1. Briefly discuss what could you do to make the implementation more robust?

The project can obviously be improved. I have selected the parameters of PID by trial and error. Manually tuning is not the best way to implement this situation. However, I can use the twiddle algorithm in order to find the PID parameters. However, this would take time. 

