# Borinot Bringup

## Hardware Checks
- [ ] The motor case should not be loose -> should be tight
- [ ] The motor ID, Spin Direction, noise in pitch -> bad -> should be clean
- [ ] Wifi antenna should be in its position (pointing up)
- [ ] on lower body, check connectors are connected
- [ ] the arm should be streched 

- Install the propellers
  - use red for top, blue for the rest
  - check that they respect the orientation of the airframe
  - check that the propeller is not damaged
  - tight the propeller

- when everything tight, turn on Borinot (with the power supply at 22.5V)

- If the radio controller does not detect the receiver, the receiver need to be bind to the radio controller
  - on the receiver, connect a jumper to the bypass pins
  - on the radio controller, start binding procedure (setting icon,`RX bind`)

## URTPS Bridge configuration
The packages of this repository use this [PX4 architecture](https://docs.px4.io/master/en/ros/ros2_comm.html) to communicate with the PX4. Not all the messages inside PX4 are broadcasted to ROS2. This is done to avoid saturating the ethernet link between the Pixhawk and the onboard computer. The messages that the Pixhawk and the onboard computer exchange cannot are set at build time by using `.yaml` files.

The `.yaml` files use to select the messages have to be configured are:
- PX4 Autopilot. You should configure this file `PX4-Autopilot/msg/tools/urtps_bridge_topics.yaml`.
- MicroRTPS Agent: You should configure this file `px4_ros_com/templates/urtps_bridge_topics.yaml`
We provide some `.yaml` files with the topics already configured depending on the type of operation that we plan to execute. You only need to copy & paste the content to the files specified above.

The files are placed in [`yaml_msgs`](https://github.com/hidro-iri/eagle_ros2/tree/devel/yaml_msgs) folder of this repo. Notice that the files with the `px4` prefix should be copied to the `PX4 Autopilot` side, whilst the ones with the `ros2` prefix should be copied to the `px4_ros_com` side.

## Software 
- 4 terminals
  - one for PX4
    ``` bash
    ssh borinot-X
    rosgalactic_cyclone
    ./start_px4
    # copy/paste the command inside the Mavlink Shell
    ```
  - one for the system
    ``` bash
    ssh borinot-X
    rosgalactic_cyclone
    ros2 launch eagle_ros2_bringup borinot_flying_arm_2_system.launch.py
    ```
  - one for the mpc
    ``` bash
    ssh borinot-X
    rosgalactic_cyclone
    ros2 launch eagle_ros2_bringup borinot_flying_arm_2_mpc.launch.py
    ```
  - one for bag record
    ``` bash
    ssh borinot-X
    rosgalactic_cyclone
    ros2 bag record -a
    ```




### [Borinot bringup](bringup.md)
