# Operation Guide

This page provides instructions for operating the Borinot using the nodes installed in it.

## Contents:
0. [**Environment Setup**](0_environment_setup.md) - Set up Ubuntu 20.04, install utility libraries, configure lab network access and enable SSH.  
1. [**Borinot Bringup**](1_borinot_bringup.md) - Install and customize PX4 firmware.
2. [**Laptop Bringup**](2_laptop_bringup.md) - Install control library with Crocoddyl dependency and Python bindings.  
3. [**Flight Procedure**](3_flight_protocol.md) - Protocol explaining how a standard flight is performed and which signs that should be looked for.

[Back to Borinot Main Page](../README.md)



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
