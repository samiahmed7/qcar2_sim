# QCar2 Simulation in Gazebo Harmonic

This repository contains the simulation for the QCar2 using ROS 2 and Gazebo Harmonic.

## Prerequisites
Ensure you have ROS 2 (Jazzy/Humble) and Gazebo Harmonic installed.

## Setup Instructions

### 1. Build the entire workspace
```bash
colcon build --symlink-install
```

### 2. Source the setup
```bash
source install/setup.bash
```

---

## Running the Simulation

### Graphics Optimization (Optional)
If you are using an **Nvidia GPU**, run these exports to improve rendering performance:
```bash
export __NV_PRIME_RENDER_OFFLOAD=1
export __GLX_VENDOR_LIBRARY_NAME=nvidia
```

### Terminal 1: Launch Gazebo
Tell Gazebo where to find the resources and launch the lab world:
```bash
export GZ_SIM_RESOURCE_PATH=~/rosbot_ws/install/qcar2/share/
gz sim -r ~/rosbot_ws/src/husarion_gz_worlds/worlds/lab_track.sdf
```

### Terminal 2: Spawn the QCar2
In a new terminal, source the workspace and create the entity:
```bash
source ~/rosbot_ws/install/setup.bash

ros2 run ros_gz_sim create -world lab_track \
  -file ~/rosbot_ws/install/qcar2/share/qcar2/urdf/QCar2.urdf \
  -name qcar2 -x 0.0 -y 0.0 -z 0.3
```
