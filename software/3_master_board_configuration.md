# Master Board Configuration

> :warning: Since some libraries are no longer actively maintained, version conflicts may occur in the future. If something doesn't work during the installation process, it could be due to a dependency that needs to be downgraded. :warning:

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
2. Use `ip address` to get the name of the interface
> :information_source: there is normally two ethernet interfaces. `eno1` is used by the Pixhawk. The master board uses the **`OTHER ONE`**.
> :information_source: Note somewhere the name of the used interface (`MY_INTERFACE`) as it will be required for thew second part.

3. Run the example inside build folder:
``` bash
cd ~/libraries/master-board/sdk/master_board_sdk/build
sudo ./master_board_example MY_INTERFACE
```
where `MY_INTERFACE` is the name of the ethernet interface used to connect to the master board.

Part 2: Odri Control Interface Installation
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
2. Test the example
```

sudo ./
```


[Next → ROS2 Workspace Configuration](4_ros2_workspace.md)
