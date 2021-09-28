# Turtlebot3 Configuration
Reference [robotis_tool](https://github.com/ROBOTIS-GIT/robotis_tools)
## PC Setup
ROS Galactic
1. Install Gazebo and Cartopgrapher
    ```
    sudo apt install ros-galactic-gazebo-*
    sudo apt install ros-galactic-cartographer
    sudo apt install ros-galactic-cartographer-ros
    ```
2. Install Navigation2
    ```
    sudo apt install ros-galactic-navigation2
    sudo apt install ros-galactic-nav2-bringup
    ```
3. Install Turtlebot3
    ```
    sudo apt install ros-galactic-dynamixel-sdk
    sudo apt install ros-galactic-turtlebot3-msgs
    ```
3. Install from source
    ```
    mkdir -p ~/colcon_turtlebot3_ws/src && cd ~/colcon_turtlebot3_ws/src
    git clone -b galactic-devel https://github.com/ROBOTIS-GIT/turtlebot3.git
    cd ~/colcon_turtlebot3_ws/src
    source /opt/ros/galactic/setup.bash
    colcon build --symling-install
    source ~/colcon_turtlebot3_ws/install/setup.bash
    ```
4. ROS Domain ID Setting In ROS2 DDS communication, **ROS_DOMAIN_ID** must be matched between Remote PC and TurtleBot3 for communication under the same network environment. Following commands shows how to assign a **ROS_DOMAIN_ID** to SBC in TurtleBot3.
    * A default ID of TurtleBot3 is *30*.
    * Configuring the **ROS_DOMAIN_ID** of Remote PC and SBC in TurtleBot3 to *30* is recommended.
    ```
    echo 'export ROS_DOMAIN_ID=30 #TURTLEBOT3' >> ~/.bashrc
    source ~/.bashrc
    ```
## Setup Raspberry PI and OpenCR
1. [Raspberry Pi Setup](docs/Raspi_Setup.md)
2. [OpenCR Setup](docs/OpenCR_Setup.md)