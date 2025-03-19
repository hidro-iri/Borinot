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
``` bash
sudo apt update
sudo apt install ros-galactic-desktop
```
2. source the ros2 environment
``` bash
source /opt/ros/galactic/setup.bash
```
3. test
``` bash
source /opt/ros/galactic/setup.bash
ros2 run demo_nodes_cpp talker
```

``` bash
source /opt/ros/galactic/setup.bash
ros2 run demo_nodes_cpp talker
```

# Part 2: ROS2 Repositories dependencies
1. **Build** and **install** vrpn from source:
``` bash
cd ~/libraries
git clone --recursive https://github.com/vrpn/vrpn.git -b master
cd vrpn
mkdir build && cd build
cmake -DCMAKE_BUILD_TYPE=Release ..
make -j6
sudo make install
```
2. **Build** and **install** hidro_utils from source:
``` bash
cd ~/libraries
git clone --recursive https://github.com/hidro-iri/hidro_utils.git -b main
cd hidro_utils
mkdir build && cd build
cmake -DCMAKE_BUILD_TYPE=Release ..
make -j6
sudo make install
```
# Part 3: ROS2 Workspace Setup
1. create the workspace `galactic_ws`
2. install vcs `sudo apt install python3_vcstool`
3. clone the repo using `vcs import < borinot.repos`
4. build using `colcon`
5. source the ros2 workspace environment
6. test
``` bash
mkdir ~/galactic_ws && cd ~/galactic_ws
```



[Back to Software](README.md)