# ROS_Project_MAP_MY_WORLD
A project using SLAM and RTAB-map to generate a map of a 3D simulated world and localize a mobile robot within it, using Gazebo, ROS and C++.

## To generate a map
### in a terminal, navigate to the catkin_ws directory and launch the project
```
$cd catkin_ws/
$source devel/setup.bash
$roslaunch my_robot world.launch
```
### launch teleop in a new terminal to control the robot
```
$cd catkin_ws/
$source devel/setup.bash
$rosrun teleop_twist_keyboard teleop_twist_keyboard.py
```
### finally, in another terminal launch the mapping program
```
$cd catkin_ws/
$source devel/setup.bash
$roslaunch my_robot mapping.launch
```
### Now, click on the terminal with the teleop program, and navigate using the keyboard. The map file will be created as the robot moves around. Revisiting locations and moving slowly can help in generating loop closures and a more accurate map. 

## To visualize the results: 
```
$rtabmap-databaseViewer ~/.ros/rtabmap.db
```

## To localize while mapping, or while using an already generated map
Follow the same instructions as for generating a map, but replace the 'mapping.launch' with 'localization.launch'
