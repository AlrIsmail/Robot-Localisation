# Robot-Localisation

## Project Overview
Welcome to the Where Am I? localization project! This project delves into the utilization of the ROS AMCL package to accurately localize a mobile robot within a map in the Gazebo simulation environments.

Throughout this project, I explore various aspects of robotic software engineering, specifically focusing on ROS:

- Creating a ROS package that launches a custom robot model in a custom Gazebo world.
- Utilizing the ROS AMCL package and the Tele-Operation / Navigation Stack to localize the robot.
- Exploring, adding, and fine-tuning specific parameters for each package to achieve optimal localization results.

## Setup

### Prerequisites
- ROS (Robot Operating System) installed on your system. You can follow the official ROS installation guide for this.
- Gazebo simulator installed.
- Understanding of ROS concepts and basic commands.

### Steps to Set Up:

1. **Create a Catkin Workspace:**
   Set up a Catkin workspace to organize your ROS packages:
   ```bash
   mkdir -p ~/catkin_ws/src
   cd ~/catkin_ws/
   catkin_make
   source devel/setup.bash
   ```

2. **Clone Project Repositories:**
   Clone the necessary repositories into your `src` directory:
   ```bash
   cd ~/catkin_ws/src
   git clone <repository_url>
   ```
   Replace `<repository_url>` with the URLs for the required repositories.

3. **Build the Workspace:**
   After cloning the repositories, build the workspace to compile the packages:
   ```bash
   cd ~/catkin_ws/
   catkin_make
   source devel/setup.bash
   ```

4. **Launch the Gazebo Simulation:**
   Run the Gazebo simulation with the custom robot model and world:
   ```bash
   roslaunch <package_name> <launch_file>.launch
   ```
   Replace `<package_name>` and `<launch_file>` with the appropriate package name and launch file.

5. **Launch AMCL and Navigation Stack:**
   Launch the ROS AMCL package along with the Navigation Stack for localization:
   ```bash
   roslaunch <amcl_package> <amcl_launch_file>.launch
   ```
   Adjust `<amcl_package>` and `<amcl_launch_file>` with the actual package and launch file names.

6. **Control the Robot:**
   - Use RViz to send 2D Navigation Goals.
   - Optionally, set up and use the teleop node to control the robot via keyboard commands:
     ```bash
     rosrun teleop_twist_keyboard teleop_twist_keyboard.py
     ```
     This step assumes the teleop package is available and configured.

7. **Test and Tune Parameters:**
   Test the localization by navigating the robot and observe its performance. Adjust parameters in the AMCL and Navigation Stack to optimize localization results.

## Testing
To evaluate the performance of your AMCL package! There are two options to control your robot while it localizes itself:

### Option 1: Send 2D Navigation Goal
You can send a 2D Nav Goal from RViz. The move_base will navigate the robot based on localization. To perform this:

1. Click the '2D Nav Goal' button in the toolbar in RViz.
2. Click and drag on the map to send the goal to the robot. It will start moving and localize itself. Use '2D Pose Estimate' to give the robot an initial position estimate on the map if needed.

### Option 2: Use Teleop Node
Alternatively, use the teleop node to control the robot and observe its localization in the environment (assuming it's set up in the Optional: Teleop Package section). Here's how:

1. Open another terminal and launch the teleop script:
   ```bash
   rosrun teleop_twist_keyboard teleop_twist_keyboard.py
   ```
2. Control your robot using keyboard commands.
