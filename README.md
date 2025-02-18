# TORCS and ROS-ES

a Low-Power Autonomous Driving Testbed with ROS and TORCS and a pun based on _Runs and Roses_

![video screenshot](https://github.com/deltaflyer/torcs-and-ros-es/blob/master/doc/images/torcs_rviz.png)

## What is included

* Ubuntu 20.04 Docker container (based on [this image](https://github.com/fcwu/docker-ubuntu-vnc-desktop/tree/bionic)) with
    * LXDE Desktop Environment
    * VNC-server that allows control from any web browser
    * ROS Noetic release
    * Extended TORCS racing simulator (patched with picture and control pipeline) ([link](https://github.com/deltaflyer/torcs-1.3.7))
    * TORCS_ROS bridge ([link](https://github.com/fmirus/torcs_ros))

## Possible Applications

* collect training data machine learning (image, sensor data, control data)
* implement and test own autonomous driving algorithms
* write bridges to existing autonomous driving frame works

## What is different from other AD-kit simulator frame works

* Low-end hardware requirements
* Batteries included (torcs / ros / bridges)
* Support of graphical desktop using any web-browser

## Usage

* Update the GIT-submodules `git submodule init && git submodule update`
* Run following script `run_environment.sh`. It builds the necessary docker image and starts the docker container.
* open a browser and goto the url `http://127.0.0.1:6080/#/`
* run `torcs` by using the desktop icon
* Get to run the _quickrace_  in the menu - you won't be able to though, it will lock expecting a car to connect from the ROS adapter
* Compile the bridge `cd workspace && catkin_make && source ./devel/setup.bash`
* Start the ROS torc bridge `roslaunch torcs_ros_bringup torcs_ros.launch`

## Requirements

* Recent Linux Distribution (64bit)
* Docker CE
* 8 GByte RAM
* 6 Gigabyte of HDD/SSD
* OpenGL > 2.0 capable graphic card

## Credits

* TORCS ROS and Patched TORCS - [Florian Mirus](https://github.com/fmirus)

## Licence

* Source code of this repository is licensed under MIT licence
* Base Docker Image - Apache license 2.0
* torcs-1.3.7 - GPL2 and other
