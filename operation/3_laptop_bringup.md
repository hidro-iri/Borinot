# Laptop Bringup

``` bash
rosgalactic_cyclone
ros2 launch eagle_ros2_viz bringup_gui.launch.py robot_name:=borinot_flying_arm_2
```

2 windows opened:
- Borinot's State: Visualizer for Borinot intern state (pose, orientation, etc)
- MPC Interface: Control the mpc and the arm

:Warning: This second window is use to send command, be careful about the value you are sending 


**Tip: Don't close these windows between flight as you can load previous command through the History**











## Additional procedures and troubleshooting

In addition to the preflight safety checklist, this page also contains documentation for other procedures that are necessary for operating the Borinot UAM. These include:




### [Troubleshooting](troubleshooting.md)

The [troubleshooting.md](troubleshooting.md) file contains a list of known issues and troubleshooting tips to help you quickly resolve problems that may arise during UAM operation.


If you encounter any difficulties during assembly or setup, our [Troubleshooting](resource/troubleshooting.md) section is here to help.

## How to Use Borinot
To use Borinot, we've made a set of guides to help you get started with it:

- [Preflight Checks](resource/preflight.md) - This document contains a checklist of preflight checks that must be performed before operating Borinot to ensure its safety and reliability.
- [Optitrack fusion](resource/optitrack.md) - This document explains how to fuse data from the Optitrack motion capture system and the PX4 flight controller to obtain accurate position and orientation estimates for Borinot.
- [MPC Controller](resource/mpc.md) - This document provides an overview of the Model Predictive Controller (MPC) used to control Borinot's hybrid locomotion, and explains how to run simulations and experiments with the controller.

[Back to HOME](../README.md)
