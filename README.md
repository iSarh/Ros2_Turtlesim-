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
**Use the arrow keys on your keyboard to control the turtle.**

![contrlTurtle](https://github.com/iSarh/Ros2_Turtlesim-/assets/63901303/fbeddfc1-a0b6-4fbb-ac03-86406e994d18)



#  Install rqt

Open a new terminal 

```bash
source /opt/ros/foxy/setup.bash
rqt
````
When running rqt for the first time, the window will be blank. **No worries**; just select **Plugins > Services > Service Caller** from the menu bar at the top.

![rqt](https://github.com/iSarh/Ros2_Turtlesim-/assets/63901303/f8df8548-5cb5-4980-b632-0429fd3a58e3)

# Spawn Service

Use rqt to call the `/spawn` service. `/spawn` will create another turtle in the turtlesim window.

![Screenshot 2024-07-04 160348](https://github.com/iSarh/Ros2_Turtlesim-/assets/63901303/f9296835-c4c0-49a5-bd06-4ae3c164fb91)


Give the new turtle a unique name, like turtle2, by double-clicking between the empty single quotes in the **expression column > name string** 

Next enter some valid coordinates at which to spawn the new turtle, like x = 1.0 and y = 1.0.

![image](https://github.com/iSarh/Ros2_Turtlesim-/assets/63901303/7696fa1e-03ff-4a38-bbe9-1f84f8561642)


call the service by clicking the **Call** button 

![image](https://github.com/iSarh/Ros2_Turtlesim-/assets/63901303/47468c2f-6139-48fd-af53-f7cb68902ea0)

# Set_pen service

Give turtle1 a unique pen using the `/set_pen service`

Set the color of the pen turtle1 and the width thickness of the line.

**Don’t forget to call the service after updating the values**

return to the terminal where `turtle_teleop_key` is running and press the arrow keys, you will see turtle1’s pen has changed.

![image](https://github.com/iSarh/Ros2_Turtlesim-/assets/63901303/7ac2c253-0b3b-478b-8322-c9208b18286e)


# Moving turtle2

You’ve probably also noticed that there’s no way to move turtle2. That’s because there is no teleop node for turtle2.

You need a second teleop node in order to control turtle2  by remapping the `cmd_vel` topic.

In a new terminal, source ROS 2, and run:

```bash
source /opt/ros/foxy/setup.bash
ros2 run turtlesim turtle_teleop_key --ros-args --remap turtle1/cmd_vel:=turtle2/cmd_vel
```
Now, you can move turtle2 when this terminal is active, and turtle1 when the other terminal running turtle_teleop_key is active.


![Remappin](https://github.com/iSarh/Ros2_Turtlesim-/assets/63901303/00c1527f-590a-4238-81b9-72fb82361f48)
