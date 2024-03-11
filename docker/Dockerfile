# This is an auto generated Dockerfile for ros:ros-base
# generated from docker_images_ros2/create_ros_image.Dockerfile.em
FROM osrf/ros:iron-desktop

RUN apt-get -y update && \
    apt-get -y install lsb-release wget gnupg

RUN wget https://packages.osrfoundation.org/gazebo.gpg -O /usr/share/keyrings/pkgs-osrf-archive-keyring.gpg && \
    echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/pkgs-osrf-archive-keyring.gpg] http://packages.osrfoundation.org/gazebo/ubuntu-stable $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/gazebo-stable.list > /dev/null && \
    apt-get -y update && \
    apt-get -y install gz-harmonic

RUN apt-get -y install ros-iron-ur && \
    apt-get -y install ros-iron-moveit*

RUN cd ~/ && \
    git clone https://github.com/jfernandez37/aprs_lab.git

RUN git clone https://github.com/UniversalRobots/Universal_Robots_ROS2_Driver.git ~/aprs_lab/aprs_ws/src/Universal_Robots_ROS2_Driver -b iron

RUN git clone https://github.com/ros-controls/gz_ros2_control.git ~/aprs_lab/aprs_ws/src/gz_ros2_control -b iron

RUN git clone https://github.com/gazebosim/ros_gz.git ~/aprs_lab/aprs_ws/src/ros_gz -b iron

RUN . /opt/ros/iron/setup.sh && \
    export GZ_VERSION=harmonic

RUN cd ~/aprs_lab/aprs_ws && \
    colcon build