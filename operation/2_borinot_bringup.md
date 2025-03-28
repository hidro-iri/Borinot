# Borinot Bringup

## Part 1: Hardware Checks
1. Check the motors:
   - [ ] Try to rotate the motor case, if it is loose, it the inside screws should be tighten
   - [ ] If some cables have been disconnected, check the motor ID and the spin direction
   - [ ] Check noise in pitch, if present, the motor should be clean
2. Check upper body:
   - [ ] Wifi antenna should be in its position (pointing up)
3. Check lower body:
   - [ ] Check connectors (Ethernet, microdriver + masterboard) are connected
   - [ ] the arm should be streched (pointing down)

## Install the propellers
1. check that the propeller is not damaged
2. Use the following color convention: red for front, blue for the rest
3. Check that they respect the orientation of the [Hexarotor X airframe reference](https://docs.px4.io/main/en/airframes/airframe_reference.html#hexarotor-x)
4. Tight the propeller

 When everything tight, turn on Borinot (with the power supply at 22.5V)

## Prepare radio controller
- Put battery in it (4x AA Batteries)
- Check if the radio controller detects the receiver (`RX` battery bar should have a voltage level -> should not be `?`)
> :warning: If the radio controller does not detect the receiver , the receiver need to be bind to the radio controller
>  - on the receiver, connect a jumper to the bypass pins
>  - on the radio controller, start binding procedure (setting icon,`RX bind`)
- Activate the Kill Switch (red switch)

## Part 2: Software Start Up
Inside Borinot `ssh borinot-X`:
1. Start `micrortps_client` in pixhawk:
    ``` bash
    ssh borinot-X
    rosgalactic_cyclone
    ./start_px4
    # copy/paste the command inside the Mavlink Shell
    ```
2. Start ros2 launch file for the system:
    ``` bash
    ssh borinot-X
    rosgalactic_cyclone
    ros2 launch eagle_ros2_bringup borinot_flying_arm_2_system.launch.py
    # the password will be asked if the arm don't start
    ```
    - You should see that the `vrpn _client_node` has fount `borinot_fur_ot`, if not, got to troubleshooting
    - If `robot_interface` don't start
    - `Warning` message should not be consider has an error
3. When using the MPC:
    ``` bash
    ssh borinot-X
    rosgalactic_cyclone
    ros2 launch eagle_ros2_bringup borinot_flying_arm_2_mpc.launch.py
    ```
  - If you need to record data, record inside Borinot
    ``` bash
    ssh borinot-X
    rosgalactic_cyclone
    ros2 bag record -a
    ```

### [Borinot bringup](bringup.md)
