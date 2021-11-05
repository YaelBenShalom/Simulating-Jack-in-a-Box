# Simulating Jack in a Box
My final project for Theory of Machine Dynamics (ME-314) course at Northwestern University.

<p align="center">
  <img align="center" src="https://github.com/YaelBenShalom/Simulating-Jack-in-a-Box/blob/main/videos/jack-in-a-box.gif">
</p>


## Table of Contents

- [Project Description](#project-description)
- [Dynamic Simulation](#dynamic-simulation)


## Project Description

In this project, I simulated and animated the dynamics of a planar jack-in-a-box system. The simulation included the dynamic of the multi-body system in time, with external forces applied on the box and impact occurs between the two rigid bodies (the jack and box’s walls).

Both bodies in the planar systems are in gravity (in the -y direction of the world frame). In addition, two external forces are applied to the box – the first is an equal and opposite force to gravity (to ensure the box stays at the same position), and the second is a torque to rotate the box. The applied torque has a sinusoidal form to make the box rotate back and forth in a constant frequency.

The system can be defined using the following configuration valuables:<br>
*q = [ x_box, y_box, θ_box,  x_jack, y_jack, θ_jack ]*

In the projects, both the jack and the box started from rest, in the initial position of *(0, 0, 0)* relative to the world frame. The world frame is fixed, while the two bodies can translate and rotate freely in the plane. In addition, I added 8 extra frames in the center of each mass to help simulate the impact’s dynamics – 4 frames on the masses of the jack and 4 frames in the center of each wall.

The following image shows the different frames of the dynamic model:

<p align="center">
  <img align="center" src="https://github.com/YaelBenShalom/Simulating-Jack-in-a-Box/blob/main/images/final-projects%20-%20frames.jpg" width="60%">
</p>


## Dynamic Simulation

To simulate the dynamic system, I used a simulation function that calculate the bodies' trajectory using their initial configuration, the time conditions and the integration law. The function uses the dynamics calculated by the Euler-Lagrange equations, and checks for impacts every single iteration.<br>
When impact is detected, the function updates the next configuration according to the impact dynamics laws.

For visualization, the simulation function plots 4 graphs for the box and jack configurations and velocities:

<p align="center">
  <img align="center" src="https://github.com/YaelBenShalom/Simulating-Jack-in-a-Box/blob/main/images/box_configuration.png">
  <img align="center" src="https://github.com/YaelBenShalom/Simulating-Jack-in-a-Box/blob/main/images/jack_configuration.png">
</p>

<p align="center">
  <img align="center" src="https://github.com/YaelBenShalom/Simulating-Jack-in-a-Box/blob/main/images/box_velocity.png">
  <img align="center" src="https://github.com/YaelBenShalom/Simulating-Jack-in-a-Box/blob/main/images/jack_velocity.png">
</p>

Jack in a box animation:

<p align="center">
  <img align="center" src="https://github.com/YaelBenShalom/Simulating-Jack-in-a-Box/blob/main/videos/ME314-final-project.gif">
</p>
