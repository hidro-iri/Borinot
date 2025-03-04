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