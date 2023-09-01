# Procedure to fly :helicopter:

- To operate with **real robots** [go here](#11-pre-flight-checklist)
- To run a **simulation** [go here](#2-simulation).

## 1 Robot procedure
### 1.1 Pre-flight checklist

- [ ] 1. Place vehicle on the ground
- [ ] 2. Ensure the security net is well mounted
- [ ] 3. Turn the transmitter on
- [ ] 4. Enable the "kill switch"
- [ ] 5. Ensure that motors' screws are tight
- [ ] 6. Ensure that propellers tight
- [ ] 7. Ensure that propellers directions are correct
- [ ] 8. Connect the power battery
- [ ] 9. Leave the flight area
- [ ] 10. Place yourself behind the operator desk with the shield
- [ ] 11. Test kill switch: Arm motors and activate kill switch. The motors must stop.
- [ ] 12. Launch QGroundControl in the GCS
- [ ] 13. Switch to manual flight mode
- [ ] 14. Launch Optitrack node to add external estimation (see [here](#px4-optitrack-position-fusion))
- [ ] 15. Change to `posctl` flight mode
- [ ] 16. Check in QGroundControl that `posctl` is enabled

After this checklist you can proceed to fly manually or to launch other systems to allow autonomous operation.

### 1.2 PX4 Optitrack position fusion
We use an Optitrack system to provide good positioning ("fake GPS") to the PX4 system. 

The Optitrack positioning is streamed via UDP. This info is gathered by a ROS node (`vrpn_client`), which broadcast this into a ROS topic. A `mavros` node is then responible to subscribe to this topic, and send this information using a serial UART port and the MAVLink protocol to the Pixhawk. Finally, this position is fused inside PX4-EKF2 with the IMU and the other enabled sensors.

*TODO: Instructions on how to launch all required elements*

### 1.3 Connect PX4 with ROS2
>:warning: **NOTE:** A prerequisite for this to work is that both (PX4 and `px4_ros_com`) have been built with the same set of messages. [See here for more info](build.md#121-urtps-bridge-configuration)
#### 1.3.1 Pixhawk 5x side
From the onboard computer do (you can connect it via SSH):
1. Access the MAVLink console `./Tools/mavlink_shell.py /dev/ttyACM0`. [More info here](https://docs.px4.io/master/en/debug/mavlink_shell.html)
3. In the MAVLink console, start the microRTPS client to start transmitting over ethernet: `micrortps_client start -t UDP -i 192.168.0.4`. Notice that the IP corresponds to the computer we want to connect with, which is the onboard computer (check the onboard computer's IP using `ifconfig`).

#### 1.3.2 Onboard computer side

1. Be sure to have configured the network setting with the correct IP (the same that you have used in the Pixhawk side).
2. Start the microRTPS agent. In a terminal from the onboard computer do: `./<path-to-ros2-ws>/install/px4_ros_com/bin/micrortps_agent -t UDP -i 192.168.0.3`.  The IP is the Pixhawk's IP.
3. Check in a separate terminal that the data is being received, e.g. `ros2 topic echo /fmu/vehicle_angular_velocity/out`

## 2 Simulation procedure
Simulation based on the SITL provided by PX4. This should be changed by our own simulation environment.

### 2.1 Simulation launch
Run the following command:
```console
foo@bar:~/$ cd <path-to-px4-autopilot>
foo@bar:<path-to-px4-autopilot>/$ make px4_sitl_rtps gazebo
```
### 2.2 Connect PX4 with ROS2
>:warning: **NOTE:** A prerequisite for this to work is that both (PX4 and `px4_ros_com`) have been built with the same set of messages. [See here for more info](build.md#121-urtps-bridge-configuration)
#### 2.2.1 Pixhawk 5x side

The MicroRTPS Client inside the PX4 should be launched automatically. You can check its status typing the following command in the PX4 shell:
```
px4> micrortps_client status
```
If it is not running, you can start it with:
```
px4> mcirortps_client start -t UDP
```
#### 2.2.2 Onboard computer side
Start the microRTPS agent. In a terminal run the following command:

```console
foo@bar:~/$./<path-to-ros2-ws>/install/px4_ros_com/bin/micrortps_agent -t UDP
```

## 3 Other useful information

### 3.1 Launch a control node

 - For the control node available [see here](../eagle_mpc_2_control/README.md)

### 3.2 ROS2 bag
To record the data in ROS2:
```
ros2 bag record -a
```
### 3.3 Launching with FastDDS

[Explanation here](https://fast-dds.docs.eprosima.com/en/v2.3.3/fastdds/ros2/ros2.html)

Steps:

1. Export environment variable: `export RMW_IMPLEMENTATION=rmw_fastrtps_cpp`

2. When running a node: `RMW_IMPLEMENTATION=rmw_fastrtps_cpp ros2 run <package> <application>`

[Back to Procedures](README.md)