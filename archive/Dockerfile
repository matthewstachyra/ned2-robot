FROM ubuntu:bionic-20220902

RUN mkdir -p /catkin_ws/src
COPY /ned_ros /catkin_ws/src/ned_ros

RUN apt-get update -q && \
    apt-get upgrade -yq && \
    apt-get install -yq wget curl git build-essential vim sudo lsb-release locales bash-completion
RUN sh -c 'echo "deb http://packages.ros.org/ros/ubuntu bionic main" > /etc/apt/sources.list.d/ros-latest.list'
RUN curl -k https://raw.githubusercontent.com/ros/rosdistro/master/ros.key | sudo apt-key add -
RUN DEBIAN_FRONTEND=noninteractive TZ=Etc/UTC apt-get -y install tzdata
RUN ECHO ""
RUN apt-get update -q && \
    apt-get install -y ros-melodic-desktop-full && \
    apt-get install -y ros-melodic-moveit && \ 
    apt-get install -y ros-melodic-rosbridge-server

ENTRYPOINT ["/bin/bash"]
