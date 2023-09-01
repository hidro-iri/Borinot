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
| Red Power Cable | 6 | 20cm Silicone 16 AWG cable in Red | [RC Innovations](https://rc-innovations.es/shop/Cable-silicona-16AWG-Rojo-1-metro-amass) |
| Black Power Cable | 6 | 20cm Silicone 16 AWG cable in Black | [RC Innovations](https://rc-innovations.es/shop/Cable-silicona-16AWG-Negro-1-metro-amass) |
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