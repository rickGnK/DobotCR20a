# 🤖 DOBOT CR20A ROS2 Integration

This repository contains my personal work and experiments with the **DOBOT CR20A** collaborative robot using **ROS 2**. The goal is to build reliable, intelligent robotic behaviors for real-world industrial applications, including motion planning, control, and AI-based perception.

---

## 🚀 Project Goals

- Integrate the DOBOT CR20A with ROS2 (Humble or Rolling)
- Develop clean and reusable control nodes
- Implement motion planning pipelines (e.g., MoveIt2)
- Connect AI/computer vision modules for smart interaction
- Build demos for real-time control and automation tasks

---

## 🛠 Features

- 🧠 ROS 2 node architecture for the CR20A
- 🎯 Motion planning examples using MoveIt2
- 📸 (Optional) Vision-based control and perception modules
- 🧩 Modular structure for easy expansion
- 💬 Logging and diagnostics tools

---

## 📦 Dependencies

- ROS 2 Humble (or compatible version)
- [MoveIt2](https://moveit.picknik.ai/)
- `rclcpp`, `sensor_msgs`, `trajectory_msgs`
- DOBOT SDK (to be linked or integrated)

Make sure to source your ROS2 workspace before running.

```bash
source /opt/ros/humble/setup.bash
```

---
# <center>ROS-Robot</center>
# 1. Introduction

DOBOT_6Axis-ROS2_V4 is a software development kit designed by Dobot based on the ROS of TCP/IP protocol. It is developed based on ROS/C++、python language, follows the Dobot-TCP-IP control communication protocol, connects to the device terminal via socket, and provides users with an easy-to-use API interface. Through DOBOT_6Axis-ROS2_V4, users can quickly connect to the Dobot device and carry out secondary development to control and use the device.



## Pre-dependency

* You can connect your computer to the network interface of the controller with a network cable, and then set the fixed IP to be in the same network segment as the controller IP. You can also connect your computer to the controller via wireless connection.

When connected via wired connection: IP: 192.168.5.1; Wireless connection: IP: 192.168.1.6

* Try pinging the controller IP to make sure it is under the same network segment.
* * Ubuntu 22.04

### Run steps

# 1. Source Code Compilation

### Download source code

```
mkdir -p ~/dobot_ws/src

cd ~/dobot_ws/src

git clone https://github.com/Dobot-Arm/DOBOT_6Axis_ROS2_V4.git

cd ~/dobot_ws
```

### Compile

```
colcon build

source install/local_setup.sh
```
### Set environment variable

```
echo "source ~/dobot_ws/install/local_setup.sh" >> ~/.bashrc
```

### Set the robot arm connection IP
```
echo "export IP_address=192.168.5.1" >> ~/.bashrc
source ~/.bashrc
```
### If it is a CR3 robot, please type the following commands

```
echo "export DOBOT_TYPE=cr3" >> ~/.bashrc
source ~/.bashrc
```

### If it is a CR5 robot, please type the following commands

```
echo "export DOBOT_TYPE=cr5" >> ~/.bashrc
source ~/.bashrc
```

### If it is a CR10 robot, please type the following commands

```
echo "export DOBOT_TYPE=cr10" >> ~/.bashrc
source ~/.bashrc
```

### If it is a CR16 robot, please type the following commands

```
echo "export DOBOT_TYPE=cr16" >> ~/.bashrc
source ~/.bashrc
```
### If it is a E6 robot, please type the following commands

```
echo "export DOBOT_TYPE=me6" >> ~/.bashrc
source ~/.bashrc
```
# 2. Demonstration

## Use in a simulation environment

## rviz display

```
ros2 launch dobot_rviz dobot_rviz.launch.py
```

You can access the joint_state_publisher_gui for each angle, and see the effect on the rviz page.

![rviz](/image/rviz.jpg)

## moveit control

* Start moveit with the following command

```
ros2 launch dobot_moveit dobot_moveit.launch.py
```

* Drag the joint to any angle and click "Plan and Execute" to see the result.

![moveit](/image/moveit.jpg)

## gazebo simulation

* Start gazebo with the following command

```
ros2 launch dobot_gazebo dobot_gazebo.launch.py 
```
![gazebo](/image/gazebo.jpg)

##  Controlling the real robot

* **Use the following command to connect to the robot**

  ```
  ros2 launch cr_robot_ros2 dobot_bringup_ros2.launch.py
  ```

* **View services**
```
ros2 service list
```
![service](/image/service.jpg)

