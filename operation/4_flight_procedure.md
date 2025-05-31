# Flight Procedure

⚠️ When flying with the MPC, two persons are required:
- One person flying the drone (on the radio controller)
- One person taking care of the MPC Interface (controlling state machine and MPC command)

> ⚠️⚠️⚠️ The person on the Radio MUST KEEP HIS/HER EYES ON BORINOT AT ALL TIMES ⚠️⚠️⚠️
>
> ⚠️⚠️⚠️ STUDY [EMERGENCY PROCEDURES](#severe-emergency-stop) BEFOREHAND ⚠️⚠️⚠️
>
> ⚠️ The person on the MPC interface should count 3..2..1..0 before sending any command

Refer to the [GUI operation guide](./3_laptop_bringup.md#launch-borinot-graphical-user-interface) to become familiar with the GUI controls and procedures.

**TIP:** If you plan to use the MPC, put the trajectory + goto command directly into the MPC Interface launched on the laptop and restart the mpc launch file. This will save time (and battery) during flight


## Part 1: Radio-controlled flight in Position Control
1. Install the battery
   - Check that the battery is full (~25V)
   - The battery cable should face front and the power cable should point top (see picture)
   - disconnect the power supply
   - Try to position the cables in order to not let them free (and possibily touch a propeller)
   - Attach the battery with the scratch
2. Enable the arm
   - > ⚠️ be sure that nothing can block the arm's motion 
   - Laptop -> MPC interface -> state machine -> Arm -> write `enable` and send request
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
4. With the radio controller ⚠️ The drone will fly!! ⚠️ 
    - Set position control:
      - Put the `SWC` switch in the middle position
    - Check Borinot's state:
      - Laptop -> Borinot state GUI -> `PX4: POSITION`
    - Desactivate the KillSwitch (red switch, top position)
    - Arm the drone with the left joystick (pointing down/right)
      -  ⚠️ The motors start spinning
      - Check if the motors are spinning properly, if something weird -> troubleshooting
      - Refer to this [link](https://docs.px4.io/main/en/flight_modes_mc/position.html) image for the command.
    - Take off slowly up
    - ⚠️ Trigger the jump
      - Climb slowly until you see borinot "jumping", then descend when the jump occurs
      - ⚠️ After each arming of Borinot, you have to trigger the jump,
      - After this, you are good to fly
    - If you want to use the MPC, read next part

## To stop the flight 

### Normal stop
At the end of an automatic flight governed by MPC (GoTo command or Trajectory command):
1. Set position control: 
   - Radio, set the `SWC` switch in the down position.
2. Enable the arm,
   - Laptop -> MPC interface -> state machine -> Arm -> write `enable` and send request
3. Land Borinot with the radio,
4. Disable the motors 
   - Radio: left joystick down-left
   - All motors stop
5. ⚠️ Activate the KillSwitch
   - Radio: red switch down
   - The robot is no longer responsive to the radio. This is a safe mode.

### Mild emergency recovery
> ⚠️ QUICK CONTROL RECOVERY ⚠️

You can interrupt any automatic flight and regain control immediately with the radio.
1. Set position control: 
   - Radio: set the `SWC` switch in the down position.
   - The control is transferred from MPC to user
   - The robot will remain in the air in position
2. [Land the robot normally](#normal-stop)

### Severe emergency stop
> ⚠️⚠️⚠️ EMERGENCY STOP ⚠️⚠️⚠️
1. ⚠️ Activate the KillSwitch
   - Radio: red switch down
2. ⚠️ All motors will stop.
3. ⚠️ THE ROBOT WILL FALL TO THE GROUND AND CRASH. 

## Part 2: Automatic flight with EAGLE MPC 
1. > ⚠️ **FOLLOW [POSITION CONTROL](#part-1-radio-controlled-flight-in-position-control) 1 TO 4 BEFORE THIS**
   - > ⚠️ Count 3..2..1..0 before sending any command
2. "Stabilize" Borinot in the air with the radio before proceeding further 
3. Enable the MPC `enable`
   - Laptop -> MPC interface -> state machine -> Controller ->  write  `enable` and send request
4. if enabled, arm the mpc with `start` command
   - Laptop -> MPC interface -> state machine -> Controller ->  write  `start` and send request
   - Borinot should stabilize and the arm will strech down, if not -> retake control (using the radio controller, switch to position control by pulling the `SWC` switch down)
5. To use the GoTo Command:
   - The origin is the same as specified for optitrack
   - The frame convention is flu (x: front, y: left, z: up)
6. To use the Trajectory command:
   - > ⚠️ ALWAYS USE RAIL MPC
   - trajectory : select one from `/home/hidro/libraries/eagle_mpc_lib/yaml/borinot_flying_arm_2/trajectories/`
   - warm start : **do not use**
   - mpc : `/home/hidro/libraries/eagle_mpc_lib/yaml/borinot_flying_arm_2/mpc/mpc.yaml`
7. You can lanuch multiple trajectories or goto commands.
8. When done, [stop the robot normally](#normal-stop)

---

| [Top of page](#flight-procedure) | [Back to Operations](./README.md) | [back to Borinot HOME](../README.md) |
| --- | --- | --- |
