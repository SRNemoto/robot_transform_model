# robot_transform_model package
Author: Shota Nemoto (srn24@case.edu)

## Start up command:
`roslaunch robot_transform_model display.launch use_xacro:=<true/false> GUI:=<true/false>`

## Startup Command arguments
- use_xacro: boolean argument that indicates whether or not to use the ROS Xacro package to generate the .urdf from urdf/robot.xacro to display in the RVIZ window 
- GUI: boolean argument that indicates whether or not to use the joint_state_publisher GUI to manipulate the continuous wheel joints.