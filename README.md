# -Launching-TurtleBot-Navigation
1. Introduction:
   
In this task, the steps to launch navigation on the TurtleBot3 robot were implemented. This includes installing the necessary packages, setting up simulation, creating a map using SLAM (Simultaneous Localization and Mapping), and launching navigation on the robot in a ROS 2 environment. 
All dependencies required for the system to function correctly were also installed.

3. Steps Taken:
   
A. Installing the TurtleBot3 Package:

The core package for TurtleBot3 was installed, which provides the necessary tools to control the robot and communicate with the rest of the system. The following command was

used to install the package:


sudo apt install ros-humble-turtlebot3

B. Installing the TurtleBot3 Simulation Package:

To run the TurtleBot3 simulation, the turtlebot3-gazebo package was installed, which provides a simulation environment using Gazebo. The following command was used:


sudo apt install ros-humble-turtlebot3-gazebo

This ensures the simulation environment is ready to use.

C. Installing the Required Navigation Packages:

To enable navigation on TurtleBot3, the core navigation packages, such as navigation2 and slam_toolbox, were installed. The following commands were used:


sudo apt install ros-humble-turtlebot3-navigation2

sudo apt install ros-humble-slam-toolbox

D. Setting Up the Environment:

The environment variable TURTLEBOT3_MODEL was set to specify the model of the robot. In this case, we used the burger model:


export TURTLEBOT3_MODEL=burger

This helps identify which robot model to use for the tasks.

E. Creating the Map Using SLAM:

To generate a map of the environment using the LIDAR sensor, SLAM was run with the robot. The following commands were used to start the process:


ros2 launch turtlebot3_bringup robot.launch.py

ros2 run slam_toolbox online_async_launch.py

These tools were used to create a map of the simulation environment.

F. Loading the Map to the Server:

After creating the map, it was loaded to the map server using the following command:


ros2 run map_server map_server /path/to/your/map.yaml

G. Launching Navigation:

Once the map was created, navigation was launched using the generated map with the following command:

ros2 launch turtlebot3_navigation2 navigation2.launch.py map:=/path/to/your/map.yaml

This ensures the robot can navigate within the environment using the generated map.

3. Verifying All Dependencies Are Installed:
   
To ensure that all required dependencies were installed correctly, the following command was used:

rosdep install --from-paths src --ignore-src -r -y

This ensures that all required packages and dependencies were successfully installed.

5. Conclusion:
   
The TurtleBot3 navigation was successfully launched in the ROS 2 environment after installing the required packages and setting up the simulation using Gazebo. A map was created using SLAM, and navigation was launched using the generated map. All required dependencies were installed correctly, and the task was successfully completed.


![لقطة شاشة 2025-02-13 220210](https://github.com/user-attachments/assets/72f46c28-3041-4aae-a639-a94927a90720)
![لقطة شاشة 2025-02-13 220059](https://github.com/user-attachments/assets/6e2c90ae-7e4b-4b88-9e0b-64ced9ab775c)
![لقطة شاشة 2025-02-13 215450](https://github.com/user-attachments/assets/9c557715-f44d-43e0-a187-9abacc6d4a9f)
![لقطة شاشة 2025-02-13 205625](https://github.com/user-attachments/assets/fcf8589c-3291-4c72-8c0b-3d8b75589e82)
![لقطة شاشة 2025-02-13 205425](https://github.com/user-attachments/assets/2ac220f7-a257-418c-a776-7a280ad74c6c)
![لقطة شاشة 2025-02-13 220603](https://github.com/user-attachments/assets/fe4b412e-351d-426c-acd9-202d090ee0f8)


