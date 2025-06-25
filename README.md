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
