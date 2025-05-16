# Eagle MPC Installation

> ⚠️  Since some libraries are no longer actively maintained, version conflicts may occur in the future. If something doesn't work during the installation process, it could be due to a dependency that needs to be downgraded. ⚠️ 


This library contains tools to solve *optimal control problems* (OCPs) that deal with *unmanned aerial manipulators* (UAMs). For more information, [read the repo](https://github.com/hidro-iri/eagle_mpc_lib).

## Part 1: Crocoddyl Installation
1. **Add** robotpkg apt repository:
> :information_source: original documentation [here](http://robotpkg.openrobots.org/debian.html)
``` bash
sudo apt install -qqy lsb-release
sudo mkdir -p /etc/apt/keyrings
curl http://robotpkg.openrobots.org/packages/debian/robotpkg.asc \
    | sudo tee /etc/apt/keyrings/robotpkg.asc
echo "deb [arch=amd64 signed-by=/etc/apt/keyrings/robotpkg.asc] http://robotpkg.openrobots.org/packages/debian/pub $(lsb_release -cs) robotpkg" \
    | sudo tee /etc/apt/sources.list.d/robotpkg.list
sudo apt update
```
2. **Configure** environment variables for robotpkg:
    - In `~/.bashrc`, add this line to the end
``` bash
# openrobot robotpkg
export PATH=/opt/openrobots/bin:$PATH
export PKG_CONFIG_PATH=/opt/openrobots/lib/pkgconfig:$PKG_CONFIG_PATH
export LD_LIBRARY_PATH=/opt/openrobots/lib:$LD_LIBRARY_PATH
export PYTHONPATH=/opt/openrobots/lib/python3.8/site-packages:$PYTHONPATH
export CMAKE_PREFIX_PATH=/opt/openrobots:$CMAKE_PREFIX_PATH
```
> ⚠️  source `~/.bashrc` or open a new terminal to pursue
3. **Install** Crocoddyl dependencies:
``` bash
sudo apt install -qqy robotpkg-py38-eigenpy=2.8.0 \
                      robotpkg-hpp-fcl=1.8.1 \
                      robotpkg-py38-hpp-fcl=1.8.1 \
                      robotpkg-pinocchio=2.6.10 \
                      robotpkg-py38-pinocchio=2.6.10 \
                      robotpkg-example-robot-data=4.1.0 \
                      robotpkg-py38-example-robot-data=4.1.0
```
4. **Build** and **install** custom Crocoddyl from source:
> :information_source: The original Crocoddyl repository has been modify to consider different stopping criteria.  
> The modified version is avalaible [here](https://github.com/PepMS/crocoddyl/tree/sbfddp-v2).
``` bash
cd ~/libraries
git clone --recursive https://github.com/PepMS/crocoddyl.git -b sbfddp-v2
cd crocoddyl
mkdir build && cd build
cmake -DCMAKE_BUILD_TYPE=Release ..
make -j6
sudo make install
```
5. **Configure** environment variables for Crocoddyl:
    - In `~/.bashrc`, add this line to the end 
``` bash
# Crocoddyl 
export PKG_CONFIG_PATH=/usr/local/lib/pkgconfig:$PKG_CONFIG_PATH
export LD_LIBRARY_PATH=/usr/local/lib:$LD_LIBRARY_PATH
export PYTHONPATH=/usr/local/lib/python3/dist-packages:$PYTHONPATH
```
> ⚠️  source `~/.bashrc` or open a new terminal to pursue

## Part 2: Eagle MPC Installation
1. **Install** Eagle MPC dependencies:
``` bash
sudo apt install libyaml-cpp-dev
```
2. **Build** and **install** Eagle MPC:
``` bash
cd ~/libraries
git clone https://github.com/hidro-iri/eagle_mpc_lib.git -b bfa2_experiments
cd eagle_mpc_lib
mkdir build && cd build
cmake -DCMAKE_BUILD_TYPE=Release -DEAGLE_MPC_URDF_DIR=/home/hidro/galactic_ws/install/hidro_robots/share/hidro_robots ..
make -j6
sudo make install
```
> ⚠️  **Problem with the system locale** ⚠️  The Yaml parser uses the `std::stod` function to convert a string to a double. This function is locale dependant. Be sure to have set a locale that uses `.` as a decimal separator. To make sure of it you can run:
``` bash
export LC_NUMERIC="en_US.UTF-8"
```
 
## Part 3: Running example
> ⚠️  A monitor connected to the computer is required to run this example

As this library contains Python bindings to its C++ code, we can run a python-based example.
1. **Install** gepetto viewer:
```bash
sudo apt install -qqy robotpkg-py38-qt5-gepetto-viewer-corba=5.8.0
```
1. **Open** viewer in one terminal:
``` bash
gepetto-gui
```
1. **Launch** the example in a second terminal:
``` bash
python3 ~/libraries/eagle_mpc_lib/examples/python/trajectory.py display
```

| [Top of page](#eagle-mpc-installation) | [Back to Software Setup Guide](README.md) | [Back to Borinot HOME](../README.md) | [Next → Master Board Configuration](3_master_board_configuration.md) |
| --- | --- | --- | --- |
