# B(erkeley) L(ocalization) A(nd) M(apping)!

***BLAM!*** is an open-source software package for fusing measurements from a wide variety of sensors in real-time for the purpose of 3D mapping and rigid body tracking. This codebase is motivated by the lack of a single universal algorithm for performing Simultaneous Localization and Mapping ([SLAM](http://wikipedia.org/simultaneous_localization_and_mapping)) across any enumeration of input data streams from different sensors. ***BLAM!*** is developed by Erik Nelson from the Berkeley AI Research Laboratory ([BAIR](http://bair.berkeley.edu)).

## Overview

***BLAM!*** supports input sensor data from 2D LiDARS, 3D LiDARS, most cameras, IMUs,
GPS devices, INS systems, and RGB-D sensors.

## Interface
***BLAM!*** is written in C++ with some Python interface elements. Input sensor
streams should be provided by the user in Robot Operating System ([ROS](http://ros.org)) format (i.e. in topic form). Currently supported ROS sensor message types include
- **2D LiDAR** as a `sensor_msgs/PointCloud2` message
- **3D LiDAR** as a `sensor_msgs/PointCloud2` message
- **IMU messages** as a `sensor_msgs/Imu` message
- **Monocular camera images** as a `sensor_msgs/Image` message
- **Stereo camera images** as a pair of `sensor_msgs/Image` messages
- **RGB-D images** as a pair of `sensor_msgs/Image` messages
- **GPS** as a `???` message

## Build Instructions
This repository contains two ROS workspaces (one internal, one external) that work, so the build process is managed by the `update` script. To build, first make sure that you do not have any other ROS workspaces in your `ROS_PACKAGE_PATH`, then clone the repository and from the top directory execute

```bash
./update
```
