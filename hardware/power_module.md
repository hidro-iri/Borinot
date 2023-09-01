# Borinot: Power Module Modification Guide

<img src="../media/power_module.png" alt="Top view of the modified power module" width="350"/>
<!-- Need picture of the modified power module, maybe from above-->

> *Power module finally modified, [**weight**] g*
<!-- Need the weight-->

The Power Module is the component responsible for distributing power among various elements, including the computer, motors, arm, and flight controller. Additionally, it monitors power consumption and battery status through the Pixhawk. This guide details the necessary modifications for its integration into Borinot.

<!-- Quick description, need to refine it-->
---

## Components list

| Part Name | Quantity | Description | Reference |
|:-|:-:|:-|:-:|
| PM03D Power Module | 1 | |[Holybro](https://holybro.com/collections/power-modules-pdbs/products/pm03d-power-module)|
| EC5-M Connector | 1 | | [TME](https://www.tme.eu/es/en/details/ec5-m/dc-power-connectors/amass/)|
| Computer Cable | 1 | 5.5mmX2.5mm barrel plug, Right Angle, [**length**] cm | [Amazon](https://www.amazon.com/Generic-5-5mm-2-5mm-Right-Pigtail/dp/B07H38LNPD)|<!-- Need the length, reference link, a proprer part name-->
|Microdriver Cable| 1 | XT30-F , [**length**] cm ||
|Masterboard Cable| 1 | [**length**] cm ||
|Pixhawk Cable| 1 |2.0mm pitch CLIK-Mate 6pin cable|[Holybro](https://holybro.com/collections/power-modules-pdbs/products/pm03d-power-module)|
<!-- Add cable detail -->

## Modification

### Part 1: Component Replacement

For the board to fit within Borinot, it's essential to modify the orientation of both the capacitor and the battery cable (currently extending outward). In our case we use battery with EC5 connectors, to facilitate manipulation, we decide to change the connector on the board side.

<!-- Need pictures above for init (with symbols on it), unsold, cable with xt60, cable with ec5, resold-->
- **Unsolder the capacitor and the battery cable from the board.**
- **Replace the battery cable's connector from XT60 to EC5.** 
  > :warning: This step depends on the battery in use.
- **Resolder the capacitor and the battery cable, ensuring they point inward.**

### Part 2: Adding Connections

To empower both the arm and the computer via the board, the VDD voltage has to be adjust to 12V and additional cables have to be solder. Also, the Pixhawk power cable has to be connected to ensure power monitoring.

<!-- Need pictures above for init (with symbol on it), microcontroller, bridge change-->
- **Set VDD to 12V by ajusting the jumper.**
- **Solder the Microdriver cable onto the [*position*] pad.** <!-- Find which pad is used-->
<!-- Need pictures on side for init (with symbol on it), computer, masterboard, pixhawk-->
- **Solder the Computer cable to the 12V pin.**
- **Solder the Masterboard cable to the 5V pin.**
- **Connect the Pixhawk power cable.**


<!-- TODO:
- Add wiring diagram
- Change cables's name
- Explain how to make the custom cable 
- Add Test and Warning and troubleshoot section
- Add cable type --> 
