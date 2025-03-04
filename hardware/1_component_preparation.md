# Borinot: Brushless Motors & ESCs Modification Guide

<img src="../media/brushless_motor.png" alt="Top view of the modified brushless motor" width="350"/>
<img src="../media/esc.png" alt="Top view of the modified esc" width="350"/>
<!-- Need picture of the modified brushless motor, maybe from above-->

> *Brushless motor and ESC finally modified, [**weight**] g and [**weight**] g respectively*
<!-- Need the weight-->

Brushless Motors enable Borinot to fly, while the ESCs manage the motors based on commands from the Pixhawk. This guide details the necessary modifications for their integration into Borinot.
<!-- Quick description, need to refine it-->
---

## Components list

| Part Name | Quantity | Description | Reference |
|:-|:-:|:-|:-:|
| TMotor F90-1300KV | 6 | | [TMotor](https://store.tmotor.com/goods.php?id=1064) |
| TMotor F35A 6s | 6 | | [TMotor](https://store.tmotor.com/goods.php?id=1176) |
| Red Power Cable | 6 | 30cm Silicone 16 AWG cable in Red | [RC Innovations](https://rc-innovations.es/shop/Cable-silicona-16AWG-Rojo-1-metro-amass) |
| Black Power Cable | 6 | 30cm Silicone 16 AWG cable in Black | [RC Innovations](https://rc-innovations.es/shop/Cable-silicona-16AWG-Negro-1-metro-amass) |
| White Servo Cable | 6 | 30cm Silicone 26 AWG cable in White | [RC Innovations](https://rc-innovations.es/shop/Cable-de-silicona-26AWG-blanco-1-metro) |
| Black Servo Cable | 6 | 30cm Silicone 26 AWG cable in Black | [RC Innovations](https://rc-innovations.es/shop/cable-de-silicona-26-awg-negro-1-metro) |
| Banana Plug | 18 | [**length**] mm, pair | [RC Innovations](https://rc-innovations.es/shop?search=conector+banana&order=) |
| XT30 Connector | 6 | Male | [RC Innovations](https://rc-innovations.es/shop/amass-conector-xt30-macho-xt30u-m) |
| Servo Connector | 6 | Female | [RC Innovations](https://rc-innovations.es/shop/Conector-servo-Futaba-hembra) |
<!-- Change cable names -->
<!-- Add connector dimensions -->
<!-- Change links -->

## Modification

### Part 1: Motor Modification

For the brushless motor, you'll need to solder the correct connector to connect it to the ESC. The existing cable is longer than necessary, so it will be trimmed. The leftover pieces from the motor's cable will be soldered to the ESC.

<!-- Need pictures above for init, cut, solder banana plug, thermoretractil-->
- **Trim the phase cables by about 5cm.**
  > :warning: Retain the leftover cables for the ESCs.
- **Solder the Male banana connectors to the phase cables.**
- **Add heat shrink tubing around the connectors to insulate the soldered joints.**
- **Repeat the steps for all 6 brushless motors.**

### Part 2: ESC Modification

The ESC connects to three components: the brushless motor (via phase cables), the power module (via power cables), and the Pixhawk (via servo cables). You must prepare all three connections for the ESC to function.

<!-- Need pictures above for init (with symbols for the cable connection), cut, solder cable to pad, connector to cable, thermo-->
- **Solder 5cm of the leftover phase cables from the brushless motor to the ESC's phase pads.**
- **Solder the Female banana connectors to these phase cables.**
- **Add heat shrink tubing around the connectors and heat to seal.**
<!-- Need pictures above for init (with symbol on it), sold pad, thermo, connector, heat-->
- **Solder the 20cm power cables to the ESC's power pads: the red cable to the + pad and the black cable to the - pad.**
- **Slide heat shrink tubing onto both power cables without heating it.**
- **Solder the XT30 male connectors to the power cables.**
  > :warning: Ensure you maintain the correct polarity.
- **Heat the tubing to seal the soldered joints.**
<!-- Need pictures above for init (with symbol on it and on connector), sold pad, crimp, connector-->
- **Solder the 30cm servo cables to the ESC's servo pads: the white cable to the signal pad and the black cable to the ground pad.**
- **Crimp the wires and attach the servo connectors.**
  > :warning: Ensure the correct orientation of wires within the connector.
- **Repeat the steps for all 6 ESCs.**

<!-- TODO:
- Add wiring diagram
- Change cables's name
- Add Test and Warning and troubleshoot section -->



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
