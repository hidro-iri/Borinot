# Building Instructions

This guide provides comprehensive assembly instructions for our airframe. The assembly process is divided into two main sections: the upper body (flying platform) and the lower body (landing gear and leg). Before you begin, ensure you have the necessary tools at hand.

## Airframe Assembly (Upper Body)

The airframe, which is part of the upper body, comprises the motors, ESCs (Electronic Speed Controllers), motor case, and the carbon fiber frame.

> :warning: **Note**: Motor identification is crucial. Please refer to the [Hexarotor X airframe reference](https://docs.px4.io/main/en/airframes/airframe_reference.html#hexarotor-x) to correctly identify each motor.

### 3D Preparation

1. Clean all 3D printed parts thoroughly.
2. Ensure all support structures, especially those inside the tube holder, are completely removed.
3. Assemble the motor marker as follows for each motor:
   
| Motor ID | Marker Position |
|:-:|:-:|
| 1 | Bottom Right |
| 2 | Top Right |
| 3 | Top Left |
| 4 | Bottom Left |
| 5 | Top Right |
| 6 | Bottom Right |

4. Attach two inserts to the bottom part.
5. Complete the assembly of the motor cache.

### Motor Wiring

1. Cut phase cables to a length of 5cm.
2. Solder the male phase connector.
3. Cover each connector with heat shrink tubing.

### ESC Wiring

For the phase:
1. Solder a 5cm cable from the motor.
2. Attach the female phase connectors.
3. Place heat shrink tubing around the full connector.

For power:
1. Solder a 20cm cable, using red for positive (+) and black for negative (-).
2. Place heat shrink tubing around the cable (do not heat yet).
3. Attach the XT18 connector.
4. Heat the tubing around the cable first, followed by the connector.

For signal:
1. Solder a 30cm cable using white for the signal and black for ground.

### Final Assembly

1. Combine the motor's top, middle, and bottom parts.
2. Secure using 4xM3x30 screws. Ensure the o-ring is positioned on the carbon tube, fitting inside the tube holder and motor.
3. Install the ESC within the motor support.
4. Secure the motor cache with 2xM3x6 screws.

---

## Lower Body Assembly

The lower body consists of:
- Landing gear
- Arm (comprising the flying link, ODRI link, and extremity)
- ODRI controller.

### Arm Assembly - Extremity

#### Components List

| Part Name | Quantity |
|:-:|:-:|
| [Extremity - 3D Kit](CAD/limbs/) | 1 |

1. Thoroughly clean the extremity part.

### Arm Assembly - ODRI Link

Refer to the [actuator module page](https://github.com/open-dynamic-robot-initiative/open_robot_actuator_hardware/blob/master/mechanics/actuator_module_v1/README.md#brushless-actuator-module-core-v1) of the ODRI project for assembly details.

### Arm Assembly - Flying Link

#### Components List

| Part Name | Quantity |
|:-:|:-:|
| [Flying link - 3D Kit](CAD/limb/) | 1 |
| Output Bearings | 2 |
| Transmission Bearings | 3 |
| M3x5mm flat head Screws | 4 |
| M3x15mm Screw | 4 |
| M3x16mm Flat Head nylon Screw | 2 |
| M3x20mm flat head Screws | 6 |
| 201mm timing belt | 1 |
| 150mm timing belt | 1 |
| M3 Nuts | 18 |
| M3 Inserts | 2 |

#### 3D Preparation

1. Clean the **Flying - 3D Kit** components thoroughly.
2. Insert **M3 Nuts**, **M3 Inserts**, **Output Bearings**, and **Transmission Bearings** in their corresponding slots in the 3D kit components.

#### Assembly

1. Secure the motor within the flying case A using 4 screws.
2. Position the 150mm timing belt around the motor's axle.
3. Install the encoder adjacent to the motor, and secure with nylon screws.
4. Place the ODRI 3D component, aligned with the 201mm timing belt. Close using flying case B and 6x20mm screws.
5. Attach the ODRI link and the extremity, securing with 15mm screws.

---

## ODRI Controller Assembly

#### Components List

| Part Name | Quantity |
|:-:|:-:|
| [Controller Case - 3D Kit](CAD/platform/) | 1 |
| Master Board | 1 |
| Micro Driver | 1 |
| M2 Nuts | 4 |
| M2.5 Nuts | 4 |
| M3 Inserts | 3 |
| M3x5mm Screws| 3 |
| M2x6mm Screws | 4 |
| M2.5x6mm Screws | 4 |

#### 3D Preparation

1. Clean all parts of the **Controller Case - 3D Kit**.
2. Insert **M2 Nuts**, **M2.5 Nuts**, and **M3 Inserts** in their designated slots in the 3D kit components.

#### Assembly

1. Secure the master board inside the controller case - top using M2 screws.
2. Mount the micro driver at the bottom of the controller case, securing with M2.5 screws.
3. Connect the two links to the micro driver. Ensure the cable routes through the designated holes in both the controller and flying cases.
4. Establish a connection between the micro driver and the master board. Close the assembly using 3 M3 screws.

---

## Landing Gear Assembly

#### Components List

| Part Name | Quantity |
|:-:|:-:|
| [Landing Gear - 3D Kit](CAD/legs/) | 1 |
| Ø20mm O-Ring Seals | 12 |
| M3x10mm Screws | 8 |
| M3x16mm Screws | 8 |
| M3 Nuts | 16 |
| Ø8mmx6mmx110.0mm Carbon Fiber Round Checked Tubes | 4 |
| Ø8mmx6mmx170.0mm Carbon Fiber Round Checked Tubes | 2 |
| Ø8mmx6mmx300.0mm Carbon Fiber Round Checked Tubes | 2 |

#### 3D Preparation

1. Clean all components of the **Landing Gear - 3D Kit**. Ensure that tube entry points are clear of any obstructions.
2. Insert **M3 Nuts** in their specified slots.
3. Place 3 **Ø20mm O-Ring Seals** around each pawn.

#### Assembly

1. Join the wye connectors and pawns with the 300mm carbon fiber tubes. Ensure alignment with provided pictures (or diagrams). Repeat the step for the second set.
2. Combine the cross-block connectors with the 170mm carbon fiber tubes, following reference images. Create two such assemblies.
3. Integrate the entire setup using the 4 110mm carbon fiber tubes, ensuring alignment with provided pictures (or diagrams).

---

We hope this assembly guide provides clarity for constructing the airframe. For any questions or additional support, please contact our technical team.
