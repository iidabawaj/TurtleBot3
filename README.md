# TurtleBot3
Task 2 of the Artificial Intelligence path
### Install and launch TurtleBot3 with SLAM approach to create and save a map

## SLAM
Simultaneous Localization and Mapping is a method used for autonomous vehicles that lets you build a map and localize your vehicle in that map at the same time. SLAM algorithms allow the vehicle to map out unknown environments.

## Install TurtleBot3 
 1. Download and Install Ubuntu
 2. Install ROS
   - 2.1 Install Dependent ROS Packages
   ``` bash
$ sudo apt-get install ros-noetic-joy ros-noetic-teleop-twist-joy \
  ros-noetic-teleop-twist-keyboard ros-noetic-laser-proc \
  ros-noetic-rgbd-launch ros-noetic-rosserial-arduino \
  ros-noetic-rosserial-python ros-noetic-rosserial-client \
  ros-noetic-rosserial-msgs ros-noetic-amcl ros-noetic-map-server \
  ros-noetic-move-base ros-noetic-urdf ros-noetic-xacro \
  ros-noetic-compressed-image-transport ros-noetic-rqt* ros-noetic-rviz \
  ros-noetic-gmapping ros-noetic-navigation ros-noetic-interactive-markers
  ```
   - 2.2 Install TurtleBot3 Packages
   ``` bash
$ sudo apt install ros-noetic-dynamixel-sdk
$ sudo apt install ros-noetic-turtlebot3-msgs
$ sudo apt install ros-noetic-turtlebot3
$ echo "export TURTLEBOT3_MODEL=burger" >> ~/.bashrc
$ source ~/.bashrc
```
## Launch TurtleBot3 
Launch gazebo and see the actual map 
``` bash
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
```
![Screenshot from 2023-08-08 22-20-04](https://github.com/iidabawaj/TurtleBot3/assets/139181626/ce6faee9-2eb4-48ce-b7c6-8fcccdf80e1a)

## Launch Rvis for SLAM
Launch Rvis and use SLAM approach to draw the map 
``` bash
$ roslaunch turtlebot3_slam turtlebot3_slam.launch
```
![Screenshot from 2023-08-09 02-09-38](https://github.com/iidabawaj/TurtleBot3/assets/139181626/379d034c-bcfa-4b72-a714-905b898c7892)

## Control the TurtleBot3
To control the movement of turtlebot3
``` bash
rosrun turtlebot3_teleop turtlebot3_teleop_key
```
## Save the Map
``` bash
rosrun map_server map_saver -f ~/map
```
![map](https://github.com/iidabawaj/TurtleBot3/assets/139181626/b9c575bd-eab0-41e9-b17f-9dd55199f6be)




