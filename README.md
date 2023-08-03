# ROS2-study
Any notes made by me during ROS2 study

1) openmanipulator ros2

- there was a compiling error while building the files in https://emanual.robotis.com/docs/en/platform/openmanipulator_p/ros2_setup/#ros-setup

added
```
#include "rclcpp/rclcpp.hpp"
```
changed 
```
this->declare_parameter("with_gripper");
```
in open_manipulator_p_teleop.cpp, open_manipulator_p_joystick.cpp, open_manipulator_p_controller.cpp to
```
this->declare_parameter("with_gripper", rclcpp::PARAMETER_BOOL);
```
(referenced from https://roboticsbackend.com/rclcpp-params-tutorial-get-set-ros2-params-with-cpp/)


solved launch errors by changing node_executable and node_name in launch.py file to
```
package='open_manipulator_p_controller',
executable='open_manipulator_p_controller',
```
(referenced from https://github.com/benbongalon/ros2-urdf-tutorial/issues/2)
