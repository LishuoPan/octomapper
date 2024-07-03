# octomapper

A tool to use the realsense and vicon to map the environment.

## Dependencies

ROS1 - Noetic

Ubuntu 20.04

realsense-ros

octomap_server

vicon_bridge



## Install Steps

### Step 1 - install the `vicon_bridge`

```
cd ~/catkin_ws/src
git clone https://github.com/ethz-asl/vicon_bridge.git
```

### Step 2 - install the `octomap_mapping` 

```
sudo apt-get install ros-noetic-octomap ros-noetic-octomap-mapping
rosdep install octomap_mapping
rosmake octomap_mapping
```

### Step 3 - Install the `realsense-ros`

follow instruction on

https://github.com/IntelRealSense/realsense-ros/tree/ros1-legacy



### Step 4 - Build

```
cd ~/catkin_ws
catkin_make
```



## How to Run

Step 1: Register the object to track in vicon application

Step 2: Change the ip address for vicon machine and object frame in rs_world_mapping.launch

Step 3: to run the octomap_server with realsense and vicon

```
cd ~/catkin_ws
source devel/setup.bash
roslaunch octomapper rs_world_mapping.launch
```

Step 4: to save the octomap

After mapping is finished and the launch file is still running, run this

```
rosrun octomap_server octomap_saver actlab.bt
```



## How it looks like

![lab](/home/lishuo/catkin_ws/src/octomapper/images/lab.jpg)

![octomap_3](/home/lishuo/catkin_ws/src/octomapper/images/octomap_3.png)