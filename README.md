# CSE 298 - Homework 2

For this assignment you will derive the relevant matrices needed to compute a prediction and measurement update for a robot moving on a 2D plane. On this plane, the robot has an `x` coordinate, a `y` coordinate, and a `theta` orientation. It moves with linear velocity `v`, and angular velocity `omega`.

The state vector `s_t` for this robot is

```
s_t = [x y theta]'
```

The input control `u_t` for the robot is

```
u_t = [v omega]'
```

The robot can make an observation `z_t` of a landmark using a LIDAR sensor. The sensor reports the range of the landmark `rho` and the bearing to the landmark `phi`.

```
z_t = [rho phi]'
```

You will need some trig for this assignment, so if you need to brush up on your sines and cosines, do so now. Remember: SOHCAHTOA.

## Model

### Question 1

Write down the range of the robot `rho` in terms of the landmark's coordinates `(m_x, m_y)`, and the robot's coordiantes `(x,y)`.

### Question 2

Write down the bearing of the robot `phi` in terms of the landmark's coordinates `(m_x, m_y)`, and the robot's coordiantes `(x,y)`.

Hint: You'll want to use `atan2()`.

### Question 3

With the answers to 1 and 2, write down the function `h(s_t)`.

### Question 4

The robot can be thought of moving along circumference of a circle with radius

```
r = v/omega
```

The velocity vector of the robot can be broken down into x and y components. What are `vx` and `vy`, given `theta`?

--

Let's say that `v` and `omega` remain constant over a small time period `dt`. If the robot starts at `x` and `y` with orientation `theta`, and it's traveling  at `v` and `omega`, where will the robot be after `dt`?

### Question 5

- x update
- y update
- theta update

### Question 6

With the answers to 5, write down the function g(s_t,u_t).

## Linearization

The model you made in the previous part is nonlinear. Those pesky sines and cosines ruin it for us. In order to use an EKF, we need to linearize the model by calculating the [Jacobian](https://en.wikipedia.org/wiki/Jacobian_matrix_and_determinant).

## Question 9

Calculate the following:

- dg(1)/dx (the derivative of g(1) with respect to x)
- dg(2)/dx
- dg(3)/dx
- dg(1)/dy
- dg(2)/dy
- dg(3)/dy
- dg(1)/dtheta
- dg(2)/dtheta
- dg(3)/dtheta

## Question 10

Write down the Jacobian matrix G using the answers to question 9

## Question 11

Calculate the following:

- dh(1)/dx
- dh(2)/dx
- dh(1)/dy
- dh(2)/dy
- dh(1)/dtheta
- dh(2)/dtheta

## Question 12

Write down the Jacobian matrix H using the answers to question 11
