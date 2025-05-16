# Eagle MPC ROS2: Control -> Decentralized controller

## 1 Architecture
## 2 Operation

### 2.1 Build with the appropriate messages
To run this node you should first have compiled the `PX4-Autopilot` and the `px4_ros_com` by using the messges in `px4_control_msgs.yaml` and `ros2_control_msgs.yaml`, respectively.

[Build procedure](../README.md#2-build)

### 2.2 Launch the required systems

1. Start the PX4 simulation:
```console
foo@bar:~/$ cd <path-to-px4-autopilot>
foo@bar:<path-to-px4-autopilot>/$ make px4_sitl_rtps gazebo
```
2. In a second terminal, source your ROS2 workspace and run the following command:
```console
foo@bar:<path-to-ros2-ws>/$ ros2 launch eagle_ros2_control decentralized_controller.launch.py
```
3. In a third termimal, publish a GoTo command:
```console
foo@bar:~$ ros2 topic pub -1 /goto_command eagle_mpc_2_interfaces/msg/GoToCmd "{platform_pos:{x: 0, y: 0, z: 2}, platform_yaw: 90}"
```
4. Now, you can enable the Decentralized controller:
```console
foo@bar:~$ ros2 service call /decentralized_controller/state_transition eagle_mpc_2_interfaces/srv/TransitionCommand "{command: enable}"
```

---

| [Top of page](#eagle-mpc-ros2-control---decentralized-controller) | [Back to Eagle MPC - ROS2 Control](README.md) | [Back to Software](../README.md) |
| --- | --- | --- |