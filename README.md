ROS 2 Jazzy Hexacopter Simulation

A custom 6-DOF drone simulation built for ROS 2 Jazzy and Gazebo, featuring GPU-Lidar integration, velocity-based flight control, and seamless keyboard teleoperation.

🚀 Features

ROS 2 Jazzy Compatible: Built and structured using modern ament_cmake standards.

Gazebo Integration: Powered by Gazebo simulation with custom visual and collision models.

GPU-Lidar Sensor: Fully configured 360-degree LiDAR sensor (/scan) for mapping and navigation tasks.

3D Velocity Control: Custom plugin configuration allowing full 6-DOF linear and angular movement via standard cmd_vel messages.

Keyboard Teleop Ready: Out-of-the-box support for teleop_twist_keyboard for manual flight control.

🛠️ Prerequisites & Dependencies

Ensure you have the following installed on your system (Ubuntu Linux):

ROS 2 Jazzy

Gazebo (GZ Sim)

ROS-Gazebo Bridges (ros_gz_bridge, ros_gz_sim)

You will also need the keyboard teleop package:

sudo apt install ros-jazzy-teleop-twist-keyboard


📦 Installation & Build

Clone this repository into your ROS 2 workspace src directory:

cd ~/ws_mobile/src
git clone https://github.com/YOUR-USERNAME/ros2-hexacopter-sim.git hexacopter_sim


Build the package using colcon:

cd ~/ws_mobile
colcon build --packages-select hexacopter_sim


Source your workspace:

source install/setup.bash


🎮 Usage

1. Launch the Simulation

Open a terminal, source your workspace, and launch the Gazebo simulation along with the robot state publisher and parameter bridge:

cd ~/ws_mobile
source install/setup.bash
ros2 launch hexacopter_sim gazebo_model.launch.py


2. Control the Hexacopter (Teleop)

Open a second terminal, source your workspace, and run the teleop node to fly the drone using your keyboard:

cd ~/ws_mobile
source install/setup.bash
ros2 run teleop_twist_keyboard teleop_twist_keyboard


⌨️ Flight Controls Reference

Linear Motion (Horizontal):

i : Move forward (+X)

, : Move backward (-X)

j : Move left (+Y)

l : Move right (-Y)

Altitude Control (Vertical):

t : Ascend / Move Up (+Z)

b : Descend / Move Down (-Z)

Rotation (Yaw):

u / o : Rotate counter-clockwise / clockwise

Stop / Hover:

k : Immediate stop

🗂️ Project Structure

hexacopter_sim/
├── launch/
│   └── gazebo_model.launch.py   # Main ROS 2 launch file
├── model/
│   └── robot.xacro              # Hexacopter URDF/Xacro model & plugins
├── parameters/
│   └── bridge_parameters.yaml   # ROS-Gazebo bridge configurations
├── CMakeLists.txt               # CMake build configuration
└── package.xml                  # Package metadata and dependencies


📜 License

Distributed under the MIT License.
