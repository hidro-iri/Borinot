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
