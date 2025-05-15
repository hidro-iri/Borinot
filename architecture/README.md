# Borinot architecture

Borinot consists of hardware and software, both within the robot body and outside as necessary support elements.

This chapter describes the architecture.

## Hardware

The Borinot robot consists of a flying platform and an arm, and is supported by some external equipments such as the Radio controller, the WIFI router, Optitrack and the base station or Laptop.

![Borinot Hardware](../media/Borinot.Hardware.png)

## Software

Borinot runs many pieces of software. Here, we detail the information flow for estimation (from sensors to computer) and control (from computer to motors). We also show the data flow for simulations.

### Software for state estimation

State estimation consists of fusing Borinot's IMU data with Optitrack position and orientation data.

The fusion is performed in the PixHawk unit by the EKF2 module.

The IMU data is gathered directly by PX4 in PixHawk

The Optitrack data is transferred from the Optitrack computer via wifi to Borinot's NUC, then via Ethernet to PX4 in Pixhawk.

The result of the estimation is send back to the NUC.

Additionally, the ODRI master board reports the arm state to the NUC via Ethernet.

Beware there are thre different reference frame conventions:
  - Optitrack uses FRU
  - PX4 uses FRD
  - ROS and Eagle MPC uses FLU
  - There is a node in NUC transforming messages

![Borinot Estimation](../media/Borinot.Estimation.png)


### Software for Control

![Borinot Control](../media/Borinot.Control.png)

### Software for Simulation

![Borinot Simulation](../media/Borinot.Simulator.png)
