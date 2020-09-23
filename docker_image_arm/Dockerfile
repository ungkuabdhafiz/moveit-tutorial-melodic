FROM arm64v8/ubuntu:18.04

RUN apt-get update && apt-get install -y lsb-release gnupg2 && apt-get clean all

RUN sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

RUN apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654

RUN apt update

ENV DEBIAN_FRONTEND=noninteractive

RUN apt install ros-melodic-desktop-full -y

RUN echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc

RUN apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential -y

RUN rosdep init

RUN rosdep update

RUN apt-get update

RUN apt-get dist-upgrade -y

RUN apt-get install ros-melodic-catkin python-catkin-tools -y


RUN apt-get install ros-melodic-moveit-core -y
RUN apt-get install ros-melodic-moveit-visual-tools -y
RUN apt-get install ros-melodic-moveit-ros-planning-interface -y
RUN apt-get install ros-melodic-moveit-ros-perception -y
RUN apt-get install -y ros-melodic-moveit-planners-ompl 
RUN apt-get install -y ros-melodic-moveit-fake-controller-manager
RUN apt-get install -y ros-melodic-moveit-ros-visualization





