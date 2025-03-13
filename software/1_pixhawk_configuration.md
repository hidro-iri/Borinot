# Pixhawk Configuration

## 1 Installation
In order to perform direct actuator control we need to modify the [original](https://github.com/PX4/PX4-Autopilot) PX4 repository. You should install [this modified version](https://github.com/hidro-iri/PX4-Autopilot).

> :warning: we use the `motor_control` branch.

Quick installation commands (the last command it is a script to install all PX4 Autopilot dependencies):
```console
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

1. [**Foonathan memory**](https://github.com/eProsima/foonathan_memory_vendor)
2. [**FastDDS**](git@github.com:eProsima/Fast-DDS.git) tag v2.0.2

#### 1.1.2 Fast-RTPS-Gen
To build **FastRTPS-Gen**, we need **Gradle**, which at the same time must be downloaded using **SDKman**. Thus we recommend to follow a reverse order:

1. Install [**SDKman**](https://sdkman.io/install)
2. Install [**Gradle**](https://docs.px4.io/master/en/dev_setup/fast-dds-installation.html#gradle). From a terminal run: `sdk install gradle 6.3`.
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


[Back to Software](../README.md)
