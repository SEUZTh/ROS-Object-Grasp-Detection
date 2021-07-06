# ROS-Object-Grasp-Detection

## Environment Configure

### UR Built from Source

```
cd ~/ws_moveit/src
git clone -b melodic-devel https://github.com/ros-industrial/universal_robot.git
# check dependencies
cd ~/ws_moveit
rosdep update
rosdep install --rosdistro melodic --ignore-src --from-paths src
# build
catkin_make
# if you're using ubuntu in vmware, you need to run this
export SVGA_VGPU10=0" >> ~/.bashrc
# modify the file, change "https://api.ignitionfuel.org" to "https://api.ignitionrobotics.org"
gedit ~/.ignition/fuel/config.yaml
# run the launch file to test the environment
roslaunch ur_gazebo ur5.launch
# For setting up the MoveIt! nodes to allow motion planning run:
roslaunch ur5_moveit_config ur5_moveit_planning_execution.launch sim:=true
# For starting up RViz with a configuration including the MoveIt! Motion Planning plugin run:
roslaunch ur5_moveit_config moveit_rviz.launch config:=true
```

