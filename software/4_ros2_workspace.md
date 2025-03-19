# ROS2 Workspace

# Part 1: ROS2 Galactic Installation
1. **Setup** sources:
``` bash
sudo apt install software-properties-common
sudo add-apt-repository universe
sudo apt update && sudo apt install curl
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null
```

1. **Install** ROS 2 packages:
```
sudo apt update
sudo apt install ros-galactic-desktop
1. source the ros2 environment
2. test

# Part 2: ROS2 Repositories dependencies
1. **Build** and **install** custom Master Board SDK from source:
> :information_source: The original Master Board SDK repository has been forked to converse an older version compatible with the rest of the system.  
> The modified version is avalaible [here](https://github.com/hidro-iri/master-board).
``` bash
cd ~/libraries
git clone --recursive https://github.com/hidro-iri/master-board.git -b flying_arm
cd master-board/sdk/master_board_sdk
mkdir build && cd build
cmake -DCMAKE_BUILD_TYPE=Release ..
make -j6
sudo make install
```
2. **Build** and **install** custom Master Board SDK from source:
> :information_source: The original Master Board SDK repository has been forked to converse an older version compatible with the rest of the system.  
> The modified version is avalaible [here](https://github.com/hidro-iri/master-board).
``` bash
cd ~/libraries
git clone --recursive https://github.com/hidro-iri/master-board.git -b flying_arm
cd master-board/sdk/master_board_sdk
mkdir build && cd build
cmake -DCMAKE_BUILD_TYPE=Release ..
make -j6
sudo make install
```
# Part 3: ROS2 Workspace Setup
4. create the workspace `galactic_ws`
5. install vsc
6. clone the repo using `vcs import < borinot.repos`
7. build using `colcon`
8. source the ros2 workspace environment
9. test

[Back to Software](README.md)