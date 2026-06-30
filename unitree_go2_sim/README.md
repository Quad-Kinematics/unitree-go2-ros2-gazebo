## Usage

### Gazebo Simulation

Launch the Gazebo simulation:

```bash
ros2 launch unitree_go2_sim unitree_go2_launch.py

```

### RVIZ Visualization

The package includes simulated LiDAR and camera sensors. Visualize the point cloud data in RVIZ:

```bash
ros2 launch unitree_go2_sim unitree_go2_launch.py rviz:=true

```

### Teleoperation

Control the robot using the keyboard:

```bash
ros2 run teleop_twist_keyboard teleop_twist_keyboard

```

## Tuning Gait Parameters

The gait configuration for the robot is found in `unitree_go2_sim/config/gait/gait.yaml`. You can modify various parameters including knee orientation, maximum velocities, stance duration, leg swing/stance height, and odometry scaling.
