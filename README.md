# Jackal_cam_laser

| RVIZ | GAZEBO |
|:-:|:-:|
| <img src="assets/RVIZ_IMAGE.png" width="400"> | <img src="assets/GAZEBO_IMAGE.png" width="400"> |



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
cd ~/Jackal_cam_lasers/
```

**Terminal 1: Launch World**

```bash
source ~/Jackal_cam_lasers/devel/setup.bash
roslaunch aws_robomaker_small_warehouse_world view_small_warehouse.launch
```

**Terminal 2: Launch Jackal**
```bash
source ~/Jackal_cam_lasers/devel/setup.bash
roslaunch jackal_gazebo spawn_jackal.launch config:=cam_laser
```

**Terminal 3: launch SLAM**
```bash
roslaunch jackal_navigation gmapping_demo.launch
```

**Terminal 4: Rviz**
```bash
rosrun rviz rviz -d ~/Jackal_cam_lasers/rviz/holo.rviz
```

**Terminal 5: ROS TCP connection**

```bash
ifconfig
```

```bash
source ~/Jackal_cam_laser/devel/setup.bash
roslaunch ros_tcp_endpoint endpoint.launch tcp_ip:=172.21.131.199 tcp_port:=10000
```


## Teleop navigation


## Waypoint navigation

```bash
roslaunch jackal_navigation amcl_demo.launch
```


```bash
ifconfig
```
