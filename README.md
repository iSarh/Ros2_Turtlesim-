# Ros2_Turtlesim-
Manipulate with turtlesim package in ROS Foxy

Set up your environment by sourcing the following:

```bash
source /opt/ros/foxy/setup.bash
```
# Install Turtlesim

Install the turtlesim package for your ROS 2 distro:

```bash
sudo apt update
sudo apt install ros-foxy-turtlesim
```
Check that the package is installed:
```bash
ros2 pkg executables turtlesim
```
The above command should return a list of turtlesim’s executables:
>turtlesim draw_square
turtlesim mimic
turtlesim turtle_teleop_key
turtlesim turtlesim_node

