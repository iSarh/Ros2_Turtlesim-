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
>turtlesim mimic
>turtlesim turtle_teleop_key
>turtlesim turtlesim_node

#Start Turtlesim

To start turtlesim, enter the following command in your terminal:
```bash
ros2 run turtlesim turtlesim_node
```

![image](https://github.com/iSarh/Ros2_Turtlesim-/assets/63901303/480f3782-96d6-4e86-b20b-1b4ac4989229)

# Use Turtlesim
Open a new terminal and source ROS 2 again
```bash
source /opt/ros/foxy/setup.bash
```
Now you will run a new node to control the turtle in the first node:

```bash
ros2 run turtlesim turtle_teleop_key
```
**Use the arrow keys on your keyboard to control the turtle. **

https://github.com/iSarh/Ros2_Turtlesim-/assets/63901303/3204707b-1b19-446f-a0e3-6d003afa4e1f



