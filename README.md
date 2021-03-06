# ucr_bot
UCR(Underwater Cleaning Robot) is a project of HOME(Human-machine Ocean Mechanic Engineering) team, College of Mechanical Engineering, Zhejiang University. UCR packages are developed on ROS. This package is a collection of packages used on UCR such as simulation package and runing-online package.

# Prerequisit
<ol>
<li> ROS(kinetic) </li>
This is all what we are based, see https://wiki.ros.org. And all of the following packages are ROS packages.
<li> epos_hardware package </li>
See https://wiki.ros.org/epos_hardware
<li> steer_drive_ros </li>
See https://wiki.ros.org/steer_drive_ros
<li> turtlebot-teleop package </li>

```$sudo apt install ros-kinetic-turtlebot-teleop```

<li> controller_manager package </li>

```$ sudo apt-get install ros-kinetic-controller-manager```
<li> ros_control package </li>

```$sudo apt-get install ros-kinetic-ros-control ros-kinetic-ros-controllers```

<li> gazebo_ros_control package </li>

```$sudo apt-get install ros-kinetic-gazebo-ros-control```

<li> timed_roslaunch package </li>

```$sudo apt-get install ros-kinetic-timed-roslaunch```

</ol>

# Getting Started
## 1. Enable the robot
The robot could be enabled either by running online(option A) or by simulating(option B). First switch to branch "master"

```$git checkout master```

### Option A: Running Online
Launch the EPOS driver. EPOS is servo motor of UCR.

```$roslaunch ucr_epos_hardware epos.launch```

Launch the basic motion controller. This controller can drive the wheels of UCR given speed and steer angle.

```$roslaunch ucr_control control.launch```

### Option B: Simulation
Launch the world in Gazebo. It will open gazebo, load the world, and start simulating the UCR hardware.

```$roslaunch ucr_gazebo ucr_empty_world.launch```

Launch the basic motion controller.

```$roslaunch ucr_control control_gazebo.launch```

## 2. Teleop
When robot is enabled, connect a xbox360 joystick to PC and launch the teleoperator

```$roslaunch ucr_teleop xbox360_teleop_from_turtlebot.launch```

Note that "*from_turtlebot" means that the source code is in turtlebot.

# Package List
* ucr_epos_hardware

Hardware driver for EPOS. Only used when running online.

* ucr_control

Integrate speed controller and steer angle controller.

* ucr_description

Describe the physical structure.

* ucr_gazebo

Based on Gazebo, a simulation tool. It provides simulation scenarios(or called "world"), also implements simulation of robot sensors and actuators.

* ucr_rviz

Based on rviz, a visualization tool.

* ucr_teleop

Based on teleoperation package of turtlebot(a popular ROS project).

* ucrbot

The raw file exported from SolidWorks.
