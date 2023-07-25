# Jackal_cam_laser

# RVIZ and Gazebo 

# RVIZ and Gazebo

<div style="display:flex;">

<div style="flex:1;">

![RVIZ](assets/RVIZ_IMAGE.png){: style="width:200px"} 

</div>

<div style="flex:1;">

![GAZEBO](assets/GAZEBO_IMAGE.png){: style="width:200px"}

</div>

</div>

### Requirements

- [Ubuntu 18.04](https://releases.ubuntu.com/18.04/) or its [wsl](https://ubuntu.com/tutorials/install-ubuntu-on-wsl2-on-windows-10#1-overview)
- [ROS melodic](https://wiki.ros.org/melodic/Installation/Ubuntu) 

> Note you might want to source your workspace from `.bashrc`



```bash

echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

### Install jackal packages

```bash
sudo apt-get install ros-melodic-jackal-simulator ros-melodic-jackal-desktop ros-melodic-jackal-navigation -y
```

### Install Realsense packages

```bash
sudo apt-get install ros-melodic-realsense2-camera
```

## Prepare the workspace
Open the subsystem:

```bash
ubuntu1804
```

Clone: 

```bash
git clone https://github.com/oscell/Jackal_cam_lasers.git
```

Go to workspace

```bash
cd ~/Jackal_cam_lasers/
```

Initiate the workspace:

```bash
catkin_init_workspace src/
catkin_make
```
## Launch simulation

```bash
source ~/Jackal_cam_lasers/devel/setup.bash
roslaunch aws_robomaker_small_warehouse_world view_small_warehouse.launch
```

```bash
source ~/Jackal_cam_lasers/devel/setup.bash
roslaunch jackal_gazebo spawn_jackal.launch config:=cam_laser
```

```bash
roslaunch jackal_navigation odom_navigation_demo.launch
```

```bash
rosrun rviz rviz -d ~/Jackal_cam_lasers/rviz/holo.rviz
```

## Teleop navigation


## Waypoint navigation

```bash
roslaunch jackal_navigation amcl_demo.launch
```


```bash
ifconfig
```
