# Master Board Configuration

Part 1: Master Board SDK Installation
1. **Build** and **install** forked Master Board SDK from source:
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

Part 1: Odri Control Interface Installation
1. **Build** and **install** forked Odri Control Interface from source:
> :information_source: The original Odri Control Interface repository has been forked to converse an older version compatible with the rest of the system.  
> The modified version is avalaible [here](https://github.com/hidro-iri/odri_control_interface).
``` bash
cd ~/libraries
git clone --recursive https://github.com/hidro-iri/odri_control_interface.git -b flying_arm
cd odri_control_interface
mkdir build && cd build
cmake -DCMAKE_BUILD_TYPE=Release ..
make -j6
sudo make install
```

[Next → ROS2 Workspace Configuration](4_ros2_workspace.md)
