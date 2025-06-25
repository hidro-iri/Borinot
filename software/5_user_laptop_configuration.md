# USER LAPTOP INSTALLATION
## Part 1: Ubuntu Installation

1. **Download** Ubuntu 20.04(.6)
   - The ISO file can be found here: [Ubuntu 20.04](https://releases.ubuntu.com/20.04/).

2. **Install** the OS on the laptop and **set** these configurations:
   - Complete installation
   - Enable third-party libraries
   - Username: `hidro`  
   - Computer name: `hidro` 

3. **Reboot** the computer and **update** the system:
   ```bash
   sudo apt update && sudo apt upgrade -y && sudo apt dist-upgrade
   ```
   > ⚠️  Do not accept the upgrade to newer Ubuntu version.

4. **Install** system tools for the next parts:
   ```bash
   sudo apt install ssh git vim curl lsb-release python3-pip python3-vcstool
   ```
---

## Part 2: Terminal Configuration

Some useful personalizations:
- **Unlimited terminal scrolling**: Open a terminal, go to *Edit → Preferences → Scrolling*, and uncheck *Limit scrollback to*.
- **Av. pag and Re. pag to search command history**: Edit `/etc/inputrc`:
  ```bash
  sudo vim /etc/inputrc
  ```
  Uncomment the following lines:
  ```
  "\e[5~": history-search-backward
  "\e[6~": history-search-forward
  ```

## Part 3: QGROUNDCONTROL
Follow [official installation instructions](https://docs.qgroundcontrol.com/master/en/qgc-user-guide/getting_started/download_and_install.html#ubuntu).

## PART 3: ROS2 ENVIRONMENT
1. Install [ROS2 Galactic](https://docs.ros.org/en/galactic/Installation/Ubuntu-Install-Debians.html) following original instalaltion instructions
2. Create folders *libraries* and *ros_galactic_ws/src* in home directory:
``` bash
cd
mkdir libraries
mkdir -pv galactic_ws/src
```
3. **Build** and **install** hidro_utils from source:
``` bash
cd ~/libraries
git clone --recursive git@github.com:hidro-iri/hidro_utils.git -b main
cd hidro_utils
mkdir build && cd build
cmake -DCMAKE_BUILD_TYPE=Release ..
make -j6
sudo make install
```
4. Clone hidro ROS2 workspace and compile hidro_robots package.
``` bash
source /opt/ros/galactic/setup.bash
cd ~/ros_galactic_ws
wget https://raw.githubusercontent.com/hidro-iri/Borinot/refs/heads/main/config/borinot_laptop.repos
cd src
vcs import < ../borinot_laptop.repos
cd ..
MAKEFLAGS="-j6" colcon build --packages-up-to hidro_robots --symlink-install
```
5. Follow instructions [eagle_mpc_installation](2_eagle_mpc_installation.md)
6. Compile eagle_ros2_viz
``` bash
cd ~/galactic_ws
MAKEFLAGS="-j6" colcon build --packages-up-to eagle_ros2_viz --event-handlers console_direct+ --cmake-args -DCMAKE_EXPORT_COMPILE_COMMANDS=ON -DCMAKE_BUILD_TYPE=Release --symlink-install
```
---

| [Top of page](#user) | [Back to Software Setup Guide](README.md) | [Back to Borinot HOME](../README.md) |  |
| --- | --- | --- | --- |
