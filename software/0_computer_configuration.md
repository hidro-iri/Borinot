# Computer Configuration

## Part 1: Ubuntu Installation

1. **Download** Ubuntu 20.04(.6)
   - The ISO file can be found here: [Ubuntu 20.04](https://releases.ubuntu.com/20.04/).

2. **Install** the OS on the NUC and **set** these configurations:
   - Minimal installation
   - Enable third-party libraries
   - Username: `hidro`  
   - Computer name: `borinot-X` (replace `X` with the number of the computer)

3. **Reboot** the computer and **update** the system:
   ```bash
   sudo apt update && sudo apt upgrade -y && sudo apt dist-upgrade
   ```
   > :warning: Do not accept the upgrade to Ubuntu 22.04.

4. **Install** system tools for the next parts:
   ```bash
   sudo apt install ssh git vim curl
   ```

5. **Setup** a static IP address for the computer:
   - Connect to the `hidro` Wi-Fi and set a fixed IP (in the router configuration) to `192.168.1.1XX`, where `XX` is the number of the computer.

6. **Create** a folder named `libraries` in `/home/hidro` to clone and build the sources in the next parts:
   ```bash
   mkdir ~/libraries
   ```

---

## Part 2: Terminal Configuration

Some useful personalizations:
- **Unlimited terminal scrolling**: Open a terminal, go to *Edit → Preferences → Scrolling*, and uncheck *Limit scrollback to*.
- **Av. pag and Re. pag to search command history**: Edit `/etc/inputrc`:
  ```bash
  sudo vim /etc/inputrc
  ```
  Uncomment the following lines:
  ```
  "\e[5~": history-search-backward
  "\e[6~": history-search-forward
  ```
- **Change color name on terminal**: Edit `~/.bashrc`:
  ```bash
  vim ~/.bashrc
  ```
  Uncomment the following line:
  ```
  force_color_prompt=yes
  ```
  Modify the following line, changing `[\033[01;32m\]` to `[\033[01;31m\]`:
  ```
  PS1='${debian_chroot:+($debian_chroot)}\[\033[01;31m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '
  ```

---

## Other: Sources

| Name                     | Link                                                                 | Version/Branch          |
|--------------------------|----------------------------------------------------------------------|-------------------------|
| crocoddyl                | [crocoddyl](https://github.com/PepMS/crocoddyl.git/)                | branch: sbfddp-v2 (HEAD)|
| eagle_mpc_lib            |                                                                      | tag: bfa2_experiments   |
| FastDDS-2.0.2            | [Fast-DDS](https://github.com/eProsima/Fast-DDS.git/)               | tag: v2.0.2 (HEAD)      |
| Fast-RTPS-Gen            | [Fast-DDS-Gen](https://github.com/eProsima/Fast-DDS-Gen.git/)       | tag: v1.0.4 (HEAD)      |
| foonathan_memory_vendor  | [foonathan_memory_vendor](https://github.com/eProsima/foonathan_memory_vendor.git) | tag: v1.3.1 (HEAD) |
| hidro_utils              | [hidro_utils](https://github.com/hidro-iri/hidro_utils)             | branch: main            |
| master-board             | [master-board](https://github.com/open-dynamic-robot-initiative/master-board.git) | commit: 410acf0 |
| odri_control_interface   | [odri_control_interface](https://github.com/open-dynamic-robot-initiative/odri_control_interface.git) | commit: 7bb4288 |
| PX4-Autopilot            | [PX4-Autopilot](https://github.com/hidro-iri/PX4-Autopilot.git)     | branch: motor_control   |
| vrpn                     | [vrpn](https://github.com/vrpn/vrpn.git)                            | commit: 601e52c         |

---

[Next → Pixhawk Configuration](1_pixhawk_configuration.md)