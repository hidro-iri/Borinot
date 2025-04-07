# Flight Procedure

:WARNING: When flying with the MPC, two persons are required:
- one flying the drone (on the radio controller)
- one taking care of the MPC Interface (controlling state machine and MPC command)

TIPs: If you plan to use the MPC, put the trajectory + goto command directly into the MPC Interface launched on the laptop and restart the mpc launch file. This will save time (and battery) during flight

## Part 1: Position Control
1. Install the battery
   - Check that the battery is full (~25V)
   - The battery cable should face front and the power cable should point top (see picture)
   - disconnect the power supply
   - Try to position the cables in order to not let them free (and possibily touch a propeller)
   - Attach the battery with the scratch
2. Enable the arm
   - :warning: be sure that nothing can block the arm motion 
   - In the laptop -> MPC interface -> state machine -> Arm,  write and send `enable`
   - If the arm do not have the correct position, see troubleshoting
3. Move Borinot to the flying area
    - When moving Borinot, grab it from the Pixhawk case (avoid putting your hand in the propeller area)
    - Better to place it to the origin, with the front point to the x direction
    - Check if the pose estimate is converging
      - x ~ 0m
      - y ~ 0m
      - z ~ 0.19m
      - qw ~ 1
      - qx ~ 0
      - qy ~ 0
      - qz ~ 0
4. With the radio controller :warning: The drone will fly ::warning:
    - put `SWC` switch in the middle position
    - check Borinot's state -> `PX4: POSITION`
    - Desactivate the KillSwitch (top position)
    - Arm the drone with the left joystick (pointing down/right)
    - Check if the motors are spinning properly, if something weird -> troubleshooting
    - Refer to this [link](https://docs.px4.io/main/en/flight_modes_mc/position.html) image for the command.
    - :WARNING: Trigger the jump
    - after each arm, you have to trigger the jump,
    - climb slowly until you see borinot "jumping", then descend when the jump occurs
    - After this, you are good to flight
    - If you want to use the MPC, read next part
5. To stop the flight
    - Enable again the arm,
    - land Borinot,
    - when landed, activate the KillSwitch

## PART 2 : EAGLE MPC 
1. **FOLLOW POSITION CONTROL 1 TO 4 BEFORE THIS**
2. "Stabilize" Borinot before following 
3. Enable the MPC `enable`
  - In the laptop -> MPC interface -> state machine -> Controller,  write and send `enable`
4. if enabled, arm the mpc with `start` command
  - In the laptop -> MPC interface -> state machine -> Controller,  write and send `start`
  - Borinot should stabilize and the arm will strech down, if not -> retake control (using the radio controller, switch to position control)
5. To use the GoTo Command:
   - The origin is the same as specified for optitrack
   - The frame convention is flu (x: front, y: left, z: up)
- ALWAYS RAIL
- trajectory : `/home/hidro/libraries/eagle_mpc_lib/yaml/borinot_flying_arm_2/trajectories/`
- warm start : **not use**
- mpc : `/home/hidro/libraries/eagle_mpc_lib/yaml/borinot_flying_arm_2/mpc/mpc.yaml`