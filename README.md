# case_study_2


![Scenario 2](/imgs/Scenario2.png "Scenario 2")

Two robots (UAV and UGV) populate the environment and the mission is to collect two cubes (green and blue). Both robots have the required capabilities: the UAV is able to fly, manipulate (it has a gripper attached), and perceive its surroundings, while the UGV is able to navigate, manipulate, perceive and scan. However, as seen from the figure, the reachability area of the UGV does not allow it to manipulate the blue cube, hence performs tasks involving green cube only.


# Dependencies:

- https://github.com/CloudRobotics-TAMP/ROS_quadrotor_simulator.git 
- https://github.com/CloudRobotics-TAMP/husky_manipulation.git

(Pay attention to the dependencies - some packages fork the original ones to guarantee the ROS Melodic compatibility)

# Example:

- Gazebo environment: 

```
roslaunch case_study_2 case_study_2_sim_bringup.launch
```

- Stow the robot arm

```
rosrun case_study_2 stow_ur5
```

- Close the gripper

```
rosrun case_study_2 close_3fgripper
```

- Open the gripper

```
rosrun case_study_2 open_3fgripper
```

- UGV MoveIt! bringup

```
roslaunch case_study_2 ugv_moveit_planning_execution.launch
```

- UGV Navigation stack bringup

```
roslaunch case_study_2 ugv_navigation.launch
```

- Apriltag

```
roslaunch case_study_2 apriltag_gazebo.launch
```

- UAV joystick control

```
roslaunch case_study_2 uav_joystick.launch
```

- UAV 3D Navigation stack bringup

```
roslaunch case_study_2 uav_3dnavigation.launch
```
