# Flight Procedure

⚠️ When flying with the MPC, two persons are required:
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
   - > ⚠️ be sure that nothing can block the arm's motion 
   - Laptop -> MPC interface -> state machine -> Arm,  write and send `enable`
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
1. Enable the arm,
   - Laptop -> MPC interface -> state machine -> Arm,  write and send `enable`
2. Set position control: 
   - Radio, set the `SWC` switch in the down position.
3. Land Borinot with the radio,
4. Disable the motors 
   - Radio: left joystick down-left
5. ⚠️ Activate the KillSwitch
   - Radio: red switch down

### ⚠️ Mild emergency recovery ⚠️
1. Set position control: 
   - Radio: set the `SWC` switch in the down position.
   - The control is transferred from MPC to user
   - The robot will remain in the air in position
   - [Land the robot normally](#normal-stop)

### ⚠️⚠️⚠️ Severe emergency stop ⚠️⚠️⚠️
1. Activate the KillSwitch
   - Radio: red switch down
2. ⚠️ The robot will fall to the ground and crash. 
3. ⚠️ All motors will stop.

## Part 2: EAGLE MPC 
1. > ⚠️ **FOLLOW POSITION CONTROL 1 TO 4 BEFORE THIS**
2. "Stabilize" Borinot in the air with the radio before proceeding further 
3. Enable the MPC `enable`
   - Laptop -> MPC interface -> state machine -> Controller,  write and send `enable`
4. if enabled, arm the mpc with `start` command
   - Laptop -> MPC interface -> state machine -> Controller,  write and send `start`
   - Borinot should stabilize and the arm will strech down, if not -> retake control (using the radio controller, switch to position control by pulling the `SWC` switch down)
5. To use the GoTo Command:
   - The origin is the same as specified for optitrack
   - The frame convention is flu (x: front, y: left, z: up)
   - > ⚠️ ALWAYS USE RAIL MPC
   - trajectory : `/home/hidro/libraries/eagle_mpc_lib/yaml/borinot_flying_arm_2/trajectories/`
   - warm start : **do not use**
   - mpc : `/home/hidro/libraries/eagle_mpc_lib/yaml/borinot_flying_arm_2/mpc/mpc.yaml`
7. You can lanuch multiple trajectories or goto commands.
6. When done, [stop the robot normally](#normal-stop)