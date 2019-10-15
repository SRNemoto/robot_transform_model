# robot_transform_model package
Author: Shota Nemoto (srn24@case.edu)

## Start up command:
`roslaunch robot_transform_model display.launch use_xacro:=<true/false> GUI:=<true/false>`

## Startup Command arguments
- use_xacro: boolean argument that indicates whether or not to use the ROS Xacro package 
    to generate the .urdf from urdf/robot.xacro to display in the RVIZ window 
- GUI: boolean argument that indicates whether or not to use the joint_state_publisher 
    GUI to manipulate the continuous wheel joints.

## Notes
- In the launch file, the use_xacro argument doesn't actually run the xacro module on 
    robot.xacro for the follwing reasons:
    - Launch file doesn't seem to generate the .urdf properly and doesn't  substitute
        ${suffix} correctly as shown in rob_desc.txt (a text file with the output from
        'rosparam get /robot_description'). For example, 'wheel_left' would show up as 
        'wheel_${suffix}', despite the substitution happening properly when running
        xacro from outside a launch file.
    - generating the urdf from the macros from 
        /opt/ros/kinetic/share/gazebo_plugins/test/xacro/laser/hokuyo.xacro doesn't 
        give an origin for the visual components of the links, and thus the links don't
        show up in rviz correctly without me manually editing them in 
        urdf_from_xacro.urdf.
