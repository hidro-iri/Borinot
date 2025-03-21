# ROS2 Workspace

> :warning: Since some libraries are no longer actively maintained, version conflicts may occur in the future. If something doesn't work during the installation process, it could be due to a dependency that needs to be downgraded. :warning:

# Part 1: ROS2 Galactic Installation
> :information_source: The official documentation can be find [here](https://docs.ros.org/en/galactic/Installation/Ubuntu-Install-Debians.html). The following is just a rewriting 
0. **Set locale**
``` bash
locale  # check for UTF-8

sudo apt update && sudo apt install locales
sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8

locale  # verify settings
```
1. **Setup** sources:
``` bash
sudo apt install software-properties-common
sudo add-apt-repository universe
sudo apt update && sudo apt install curl
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null
```
2. **Install** ROS 2 packages:
``` bash
sudo apt update
sudo apt install ros-galactic-desktop ros-dev-tools
```
3. source the ros2 environment
``` bash
source /opt/ros/galactic/setup.bash
```
1. test
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
git clone --recursive git@github.com:hidro-iri/hidro_utils.git -b main
cd hidro_utils
mkdir build && cd build
cmake -DCMAKE_BUILD_TYPE=Release ..
make -j6
sudo make install
```
# Part 3: ROS2 Workspace Setup
1. create the workspace `galactic_ws`
2. install vcs `sudo apt install python3_vcstool`
3. clone the repo using `vcs import < borinot_onboard.repos`
4. build using `colcon`
``` bash
cd ~/galactic_ws
colcon build --event-handlers console_direct+ --cmake-args -DCMAKE_EXPORT_COMPILE_COMMANDS=ON -DCMAKE_BUILD_TYPE=Release --symlink-install
```
> :warning: **KNOWN ISSUE**: :warning:  
``` bash
CMake Error in eagle_ros2/eagle_mpc_controller/CMakeLists.txt:
Imported target "eagle_mpc" includes non-existent path
"/usr/lib/x86_64-linux-gnu/cmake/yaml-cpp/../../../../../include"
```
> In case the compilation throws this error, the include path in the `/usr/lib/x86_64-linux-gnu/cmake/yaml-cpp/yaml-cpp-config.cmake` file must be changed.  
> Change line 8, where the path is set to the following: `set(YAML_CPP_INCLUDE_DIR "${YAML_CPP_CMAKE_DIR}/../../../../include")`.  
> **Important**: eagle_mpc_lib has to be recompile before running `colcon build` 
5. source the ros2 workspace environment
6. test
``` bash
mkdir ~/galactic_ws && cd ~/galactic_ws
```
7. Add a new alias in `.bash_aliases`:
``` bash
alias rosgalactic='source /opt/ros/galactic/setup.bash && source /usr/share/colcon_argcomplete/hook/colcon-argcomplete.bash'
alias rosgalactic_cyclone='source /home/hidro/galactic_ws/install/setup.bash && cd /home/hidro/galactic_ws && export RMW_IMPLEMENTATION=rmw_cyclonedds_cpp && export CYCLONEDDS_URI=/home/hidro/galactic_ws/src/eagle_ros2/eagle_ros2_bringup/config_dds/cyclone_dds_nuc.xml'
```

8. Modify `odri_ros2/odri_interface/config/robots/flying_arm_2.yaml`

[Back to Software](README.md)