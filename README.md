# Unitree Go2 ROS2

<p align="center">
  <img src="https://oss-global-cdn.unitree.com/static/c487f93e06954100a44fac4442b94d94_288x238.png" alt="Unitree Go2" />
</p>

> **Note:** This repository is an extended and modified version of the original `unitree_go2_ros2` package by [khaledgabr77](https://github.com/khaledgabr77/unitree_go2_ros2). It introduces new custom capabilities, specifically tailored SLAM integrations.

## Overview

This package provides a complete ROS 2 Jazzy integration for the Unitree Go2 quadrupedal robot using the CHAMP controller framework. Alongside the core simulation and control capabilities, this extended version introduces advanced mapping (SLAM) configurations for autonomous research and operation.

## About Unitree Go2 & CHAMP

The Go2 is a highly capable quadrupedal robot by Unitree Robotics. This repository controls it using CHAMP (Coupled Hybrid Automata for Mobile Platforms), an open-source hierarchical control system that combines pattern modulation and impedance control for efficient locomotion.

![CHAMP Controller](https://raw.githubusercontent.com/chvmp/champ/master/docs/images/robots.gif)

## Key Features & New Additions

- ✅ Complete ROS 2 Jazzy integration & Gazebo Harmonic simulation support
- ✅ URDF model adapted to ROS 2 control framework
- ✅ SLAM (`unitree_go2_slam`): Full Simultaneous Localization and Mapping functionality enabled for 2D/3D environment reconstruction and spatial awareness.
- ✅ Integrated gait control, teleoperation, and RVIZ visualization
- ✅ Simulated sensors:
  - IMU
  - 2D LiDAR (Hokuyo)
  - 3D LiDAR (Velodyne & 4D Lidar L1)
  - Mono & Depth Cameras
- ✅ Navigation 2 integration (Coming soon)

## System Requirements

- Ubuntu 24.04
- ROS 2 Jazzy
- Gazebo Sim Harmonic

## Installation

### 1. Install ROS 2 Dependencies

```bash
sudo apt update
sudo apt install ros-jazzy-gazebo-ros2-control
sudo apt install ros-jazzy-xacro
sudo apt install ros-jazzy-robot-localization
sudo apt install ros-jazzy-ros2-controllers
sudo apt install ros-jazzy-ros2-control
sudo apt install ros-jazzy-velodyne
sudo apt install ros-jazzy-velodyne-description
```

### 2. Clone the Workspace

```bash
cd ~/ros2_ws/src
# Replace with your actual repository URL
git clone <YOUR_REPOSITORY_URL>

```

### 3. Install Dependencies

```bash
cd ~/ros2_ws
rosdep update
rosdep install --from-paths src --ignore-src -r -y

```

### 4. Build the Workspace

```bash
cd ~/ros2_ws
colcon build
source install/setup.bash

```

## Project Structure

This workspace has been restructured and expanded from the base version to accommodate the new autonomous features. The core packages include:

```text
unitree_go2_ros2/
├── champ/                      # Core controllers and state estimation for CHAMP
├── champ_base/                 # Core node configurations and hardware interfaces
├── champ_msgs/                 # Custom ROS 2 message definitions for CHAMP
├── unitree_go2_description/    # URDF models, meshes, and Gazebo world files
├── unitree_go2_sim/            # Simulation launch files and configuration parameters
└── unitree_go2_slam/           # [NEW] SLAM configurations, launch files, and mapping nodes

```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'feat: Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## Acknowledgements

A massive thank you to the developers whose foundational work made this project possible. This repository builds upon and incorporates work from the following:

- **[khaledgabr77/unitree_go2_ros2](https://github.com/khaledgabr77/unitree_go2_ros2)** - The base repository this project was forked/derived from.
- [Unitree Robotics](https://github.com/unitreerobotics/unitree_ros) - For the Go2 robot description (URDF model)
- [CHAMP](https://github.com/chvmp/champ) - For the quadruped controller framework
- [CHAMP Robots](https://github.com/chvmp/robots) - For robot configurations and setup examples
- [unitree-go2-ros2](https://github.com/anujjain-dev/unitree-go2-ros2) - ROS 2 package with gazebo classic
