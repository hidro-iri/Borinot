# Borinot 🐝

<img src="media/borinot_agile.png" width="350">

Borinot is an open-source Unmanned Aerial Manipulator (UAM), developed by the HiDRo group. This torque-controlled robot is designed for hybrid flying and contact loco-manipulation. It utilizes its extremity as a tail for flying locomotion, a hand for agile aerial manipulation, or a leg for hybrid aerial-contact locomotion. You can watch Borinot in action [here](https://www.youtube.com/watch?v=Ob7IIVB6P_A).

<!-- Quick section of the main software associate with it: eagle_mpc_lib -->
<!-- Add section ## Why Borinot Exists -->

## Assembly and Setup Guide
Before deploying Borinot, ensuring a proper assembly and configuration is pivotal. To guide you through this process, we've created detailed instructions for the robot's assembly and its software configuration:

- **[Hardware](hardware/README.md)**
  - [Components List](hardware/components_list.md) - A comprehensive list of all parts you'll need.
  - [Building Instructions](hardware/building_instructions.md) - Step by step guide to build Borinot.
  
- **[Software](software/README.md) :warning: In construction**
  - [Borinot Bringups](resource/bringup.md) - Steps required to bring up the various subsystems of Borinot, including the flight controller, manipulator, and sensors.

If you encounter any difficulties during assembly or setup, our [Troubleshooting](resource/troubleshooting.md) section is here to help.


## How to Use Borinot
To use Borinot, we've made a set of guides to help you get started with it:

- [Preflight Checks](resource/preflight.md) - This document contains a checklist of preflight checks that must be performed before operating Borinot to ensure its safety and reliability.
- [Optitrack fusion](resource/optitrack.md) - This document explains how to fuse data from the Optitrack motion capture system and the PX4 flight controller to obtain accurate position and orientation estimates for Borinot.
- [MPC Controller](resource/mpc.md) - This document provides an overview of the Model Predictive Controller (MPC) used to control Borinot's hybrid locomotion, and explains how to run simulations and experiments with the controller.

## Citing
If you use Borinot in your research work, please acknowledge our work by citing the following paper:

> :warning: **[Citation Information Pending]**
<!-- Add citation when available -->

## License

Borinot is licensed under the BSD 3-clause license. You can read the full license [here](LICENSE.md).

[Back to HiDRo Group](../profile/README.md)
