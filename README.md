ROS 2 Jazzy Hexacopter Simulation

A high-performance 6-DOF hexacopter simulation package built for ROS 2 Jazzy and Gazebo. This project features GPU-Lidar integration, 3D velocity-based flight control, and seamless keyboard teleoperation, providing a robust foundation for drone navigation and sensing experiments.

🚀 Features

Custom URDF: Complete modular robot description utilizing xacro for clear structural management.

Gazebo Integration: Ready-to-use configuration for modern Gazebo/GZ Sim using ros_gz_bridge.

LiDAR Simulation: Generates standard sensor_msgs/LaserScan data for demonstration of sensor integration and environmental scanning.

Ready to Launch: Pre-configured launch file to bring up the simulated environment, robot state publisher, and parameter bridges simultaneously.

📋 Prerequisites

Ensure you have the following installed on your system before proceeding:

ROS 2 (Jazzy)

Gazebo (Modern Gazebo / GZ Sim)

Install the required ROS 2 dependencies:

sudo apt update
sudo apt install ros-${ROS_DISTRO}-xacro ros-${ROS_DISTRO}-ros-gz-sim ros-${ROS_DISTRO}-teleop-twist-keyboard


🛠️ Installation & Build

Navigate to the source directory of your ROS 2 workspace:

cd ~/ws_mobile/src


Clone this repository:

git clone https://github.com/YOUR-USERNAME/ros2-hexacopter-sim.git hexacopter_sim


Build the package:

cd ~/ws_mobile
colcon build --packages-select hexacopter_sim
source install/setup.bash


🎮 Usage

1. Launch the Simulation

ros2 launch hexacopter_sim gazebo_model.launch.py


2. Control the Drone

In a separate terminal, use the teleop keyboard node to maneuver the hexacopter:

ros2 run teleop_twist_keyboard teleop_twist_keyboard


Move: i (Forward), , (Backward), j (Left), l (Right)

Altitude: t (Ascend), b (Descend)

Rotate: u (Counter-Clockwise), o (Clockwise)

Stop: k

📜 License

Distributed under the MIT License.
