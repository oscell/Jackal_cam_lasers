# Jackal_cam_laser

## Prepare the workspace

Clone: 

```bash
git clone https://github.com/oscell/SymbioticRobots.git
```

Open the subsystem:

```bash
ubuntu1804
```

Go to workspace

```bash
cd SymbioticRobots/jackal_ws
```

Initiate the workspace:

```bash
catkin_init_workspace src/
catkin_make
```
## Launch simulation

```bash
source devel/setup.bash
roslaunch aws_robomaker_small_warehouse_world view_small_warehouse.launch
```

```bash
source devel/setup.bash
roslaunch jackal_gazebo spawn_jackal.launch config:=cam_laser
```

```bash
roslaunch jackal_navigation odom_navigation_demo.launch
```

## Waypoint navigation
```bash
roslaunch jackal_navigation amcl_demo.launch
```
```bash
rviz rviz
```




```bash
ifconfig
```
