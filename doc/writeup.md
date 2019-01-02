# Udacity Project: Where Am I?

## Abstract

## Introduction

## Background

## Results

## Model Configuration

## Discussion

## Future Work



## Temp Collection

22.07.18
* setup catkin_ws
* prepare catkin_package udacity_bot 
* setup worlds/udacity.world for gazebo with basic elements ground/sun/camera
* setup launch/udacity_world.launch file for gazebo udacity world
* create urdf/udacity_bot.xacro defining a rudimentary Unified Robot Description Format definition for my sample robot
* add launch/robot_description.launch to load urdf model into ROS param server, 
    * add launch to udacity_world.launch
    * add urdf_launcher node to udacity_world.launch file
* add wheels to urdf-xacro model (links and joints)
* add camera and hokuyo laser range sensor to urdf model


# parameter tuning
parameters:
# costmap params
## avoid bumping into obstacles by defining robot bounding box (or in this case bounding radius) and inflation_radius for local and global costmap which favors staying away from walls when calculating pathing
robot_radius: 0.25
inflation_radius: 0.5

# planner/controller params:
## stability of control loop, limit max velocity
max_vel_x: 0.4

## increase sim_time to 4sec to achieve better/smoother prediction for the local path planner
sim_time: 4.0 

## limit controller_frequency to deterministically achievable computational performance
controller_frequency: 10Hz


# amcl
## increase number of beams for quicker convergence of pose estimation
laser_max_beams: 60 

# reduce sample interval 
resample_interval: 1





05.12.18
* create own lw_udacity_bot
* copy udacity_bot.(gazebo|xacro) -> lw_udacity_bot.(gazebo|xacro)

