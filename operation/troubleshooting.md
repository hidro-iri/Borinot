# Troubleshooting
## Problem 1:
### Error:

`what():  Unexpected byte value in Cdr::deserialize(bool), expected 0 or 1`

### Diagnostic:

PX4 messages are different from the ROS2 messages

### Solution:

1. Generate ROS2 messages using the python script
2. Remove build/ install/ log/ folders from ROS2 workspace (only px4_msgs folders)
3. Compile again ROS2 workspace

[Back to Procedures](../README.md)


## Problem: motor not spinning at the same speed

### Recalibrate the esc




## ERROR at motor driver ## : SPI Receiver timeout
- This error can occur randomly
- to solve it:
  1. kill `system.launch.py` 
  2. restrech the arm (pointing down)
  3. disconnect and reconnect the two power cables (udriver and master board)
  4. restart the `system.launch.py`
  5. reable the arm throught the MPC Interface
  6. If the arm is in it's correct starting position, you are good! 
