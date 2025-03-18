# Pixhawk Configuration

    :warning: Since some libraries are no longer actively maintained, version conflicts may occur in the future. If something doesn't work during the installation process, it could be due to a dependency that needs to be downgraded. :warning:

In this part we will install all the libraries to flash and interact with the pixhawk.

## Part 1: Dependencies Installation

1. **Install** custom PX4 from source
   > the original PX4 repository has been modify in order to perform direct actuator control.  
   >The modified version is avalaible [here](https://github.com/hidro-iri/PX4-Autopilot).
   ``` bash
   cd ~/libraries
   git clone --recursive https://github.com/hidro-iri/PX4-Autopilot.git -b motor_control
   cd PX4-Autopilot
   ./Tools/setup/ubuntu.sh
   # reboot
   ```
   :warning: **Reboot** the computer.
1. **
    ``` shell
    cd ~/libraries
    git clone --branch v1.3.1 https://github.com/eProsima/foonathan_memory_vendor
    cd foonathan_memory_vendor
    mkdir build && cd build
    cmake .. 
    make
    sudo make install 
    ```
2. Fast-DDS (previously FastRTPS)
3. FAST-DDS-Gen (previously Fast-RTPS-Gen)
4. Installation

## 1 Installation
In order to perform direct actuator control we need to modify the [original](https://github.com/PX4/PX4-Autopilot) PX4 repository. You should install [this modified version](https://github.com/hidro-iri/PX4-Autopilot).

> :warning: we use the `motor_control` branch.

Quick installation commands (the last command it is a script to install all PX4 Autopilot dependencies):
```shell
foo@bar:~$ cd libraries
foo@bar:libraries$ git clone --branch motor_control https://github.com/hidro-iri/PX4-Autopilot.git
foo@bar:libraries$ cd PX4-Autopilot
foo@bar:libraries/PX4-Autopilot$  git submodule update --init --recursive
foo@bar:libraries/PX4-Autopilot$  ./Tools/setup/ubuntu.sh
```

> :warning: "Relogin or reboot computer before attempting to build NuttX targets"

### 1.1 Dependencies: FastDDS & Fast-RTPS-Gen

#### 1.1.1 Fast-DDS
To build **FastDDS**, **Foonathan memory** is required. Both installation procedures are explained at the PX4 wiki.

```
sudo apt install libasio-dev libtinyxml2-dev
```

1. [**Foonathan memory**](https://github.com/eProsima/foonathan_memory_vendor)

``` shell
cd ~/libraries
git clone --branch v1.3.1 https://github.com/eProsima/foonathan_memory_vendor
cd foonathan_memory_vendor
mkdir build && cd build
cmake .. 
make
sudo make install 
```

1. [**Fast CDR**](https://github.com/eProsima/foonathan_memory_vendor)

``` shell
cd ~/libraries
git clone --branch v1.3.1 https://github.com/eProsima/foonathan_memory_vendor
cd foonathan_memory_vendor
mkdir build && cd build
cmake .. 
make
sudo make install 
```

2. [**FastDDS**](https://github.com/eProsima/Fast-DDS/tree/v2.0.2) tag v2.0.2

``` shell
sudo apt install 
cd ~/libraries
git clone --branch v2.0.2 https://github.com/eProsima/Fast-DDS.git
cd Fast-DDS
git submodule update --init --recursive
mkdir build && cd build
cmake .. 
make
sudo make install 
```

#### 1.1.2 Fast-RTPS-Gen
To build **FastRTPS-Gen**, we need **Gradle**, which at the same time must be downloaded using **SDKman**. Thus we recommend to follow a reverse order:

1. Install [**SDKman**](https://sdkman.io/install)
2. Install [**Gradle**] From a terminal run: `sdk install gradle 6.3`.
3. Follow [these steps](https://github.com/eProsima/Fast-DDS-Gen/tree/v1.0.4) to build **Fast-RTPS-Gen**. tag v1.0.4

## 2 Build

### 2.1 URTPS Bridge configuration
The packages of this repository use this [PX4 architecture](https://docs.px4.io/master/en/ros/ros2_comm.html) to communicate with the PX4. Not all the messages inside PX4 are broadcasted to ROS2. This is done to avoid saturating the ethernet link between the Pixhawk and the onboard computer. The messages that the Pixhawk and the onboard computer exchange cannot are set at build time by using `.yaml` files.

The `.yaml` files use to select the messages have to be configured are:
- PX4 Autopilot. You should configure [this file](https://github.com/hidro-iri/PX4-Autopilot/blob/motor_control/msg/tools/urtps_bridge_topics.yaml).
- MicroRTPS Agent: You should configure [this file](https://github.com/hidro-iri/px4_ros_com/blob/master/templates/urtps_bridge_topics.yaml)

We provide some `.yaml` files with the topics already configured depending on the type of operation that we plan to execute. You only need to copy & paste the content to the files specified above.

The files are placed in [`yaml_msgs`](https://github.com/hidro-iri/eagle_ros2/tree/devel/yaml_msgs) folder of this repo. Notice that the files with the `px4` prefix should be copied to the `PX4 Autopilot` side, whilst the ones with the `ros2` prefix should be copied to the `px4_ros_com` side.

### 2.2 Build the PX4-Autopilot

There are two options here:
- **Simulation**: 
```console
foo@bar:~$ cd <path-to-px4>
foo@bar:<path-to-px4>$ make px4_sitl_rtps
```     
- **Pixhawk**: 
```console
foo@bar:~$ cd <path-to-px4>
foo@bar:<path-to-px4>$ make px4_fmu-v5x_rtps
```

To upload the firmware to the Pixhawk-v5x, connect the flight controller using the USB and do:
```console
foo@bar:~$ cd <path-to-px4>
foo@bar:<path-to-px4>$ make px4_fmu-v5x_rtps upload
```

I have just follow that instructions
In NUC:
mkdir libraries && cd libraries

git clone --branch v1.3.1 https://github.com/eProsima/foonathan_memory_vendor.git
cd foonathan_memory_vendor && mkdir build && cd build
cmake -DCMAKE_BUILD_TYPE=Release ..
make -j6
sudo make install
cd ~/libraries

git clone –branch v2.0.2 https://github.com/eProsima/Fast-DDS.git
cd Fast-DDS 
git submodule update --init --recursive
mkdir build && cd build
cmake -DTHIRDPARTY=ON -DSECURITY=ON ..
make -j6
sudo make install
cd ~/libraries

git clone --branch v1.0.4 –recursive https://github.com/eProsima/Fast-DDS-Gen.git
cd Fast-DDS-Gen
git submodule update --init --recursive
cd gradle/wrapper/
vim gradle-wrapper.properties change DistributionUrl to 6.8.3
cd ../..
./gradlew assemble && sudo env "PATH=$PATH" ./gradlew install

pip install empy==3.3.4

Saltamos a este punto
cd ~/libraries/PX4-Autopilot/
make px4_fmu-v5x_rtps upload







[Next → Eagle MPC Configuration](2_eagle_mpc_installation.md)
