# Component Preparation Guide

Some components require modifications before assembling. This guide covers adjustments needed for the power module, brushless motors, and ESCs.

---

## 1. Power Module Modification

The Power Module distributes power to all components (computer, motors, arm, flight controller) and monitors battery status via Pixhawk.

### Materials
<img src="../media/1_power_module_exploded.avif" alt="Exploded view of power module components" width="400">

| Part Name | Quantity | Description | Reference |
|-----------|----------|-------------|-----------|
| PM03D Power Module | 1 | Base unit | [Holybro](https://holybro.com/products/pm03d-power-module) |
| EC5-M Connector | 1 | Male battery connector | [TME](https://www.tme.eu/es/en/details/ec5-m/dc-power-connectors/amass/) |
| XT30-F Connector | 1 | Female power connector | [RC Innovations](https://rc-innovations.es/shop/amass-conector-xt30-hembra-xt30u-h) |
| XT30-M Connector | 1 | Male power connector | [RC Innovations](https://rc-innovations.es/shop/amass-conector-xt30-macho-xt30u-m) |
| Diode | 1 | BQ30TB 45B714 | |
| Red Power Cable | 2 | 15cm 16AWG (VCC) | [RC Innovations](https://rc-innovations.es/shop/Cable-silicona-16AWG-Rojo-1-metro-amass) |
| Black Power Cable | 2 | 15cm 16AWG (GND) | [RC Innovations](https://rc-innovations.es/shop/cable-de-silicona-26-awg-negro-1-metro) |
| Computer Cable | 1 | 24cm barrel plug (5.5×2.5mm) | [Amazon](https://www.amazon.com/Generic-5-5mm-2-5mm-Right-Pigtail/dp/B07H38LNPD) |
| Masterboard Cable | 1 | 17cm 5V line | Custom |

### Steps
<img src="../media/1_power_module_step_1.avif" alt="Reposition current component" width="400">

- **Unsolder** the capacitor and the battery cable from the board.
- **Replace** the battery cable's connector from XT60 to EC5.
- **Repose** the capacitor and the battery cable, ensuring they point **inward** the board.

<img src="../media/1_power_module_step_2.avif" alt="Hot swap components" height="400">

- **Bend** the anode of the diode (right leg) to align with the positive terminal of the XT30-M connector (as shown in the picture) and **solder** it.  
- **Solder** the cathode of the diode (left leg) to the positive power cable.  
- **Solder** the negative power cable to the negative terminal of the XT30-M connector.  
- **Add** heat shrink tubing around the connectors and **heat** to seal, creating a **hot-swap cable**.  
- **Solder** the hot-swap cable to the original battery cable location, maintaining the same orientation.  

<img src="../media/1_power_module_step_3.avif" alt="Microdriver components" width="400">

- **Solder** the two power cables to XT30 connector (red cable to the positive terminal, black cable to the negative terminal).
- **Add** heat shrink tubing around the connectors and **heat** to seal, creating a **microdriver cable**.  
- **Solder** the microdriver cable to the pad **located on top of the Pixhawk connector** (red cable to B+ pad, black cable to GND pad).

<!-- Need pictures on side for init (with symbol on it), computer, masterboard, pixhawk-->
- **Solder the Masterboard cable to the 5V pin.**

<img src="../media/1_power_module_step_5.avif" alt="Computer components" height="400">

- **Set VDD to 12V** using the jumper configuration.  
- **Cut** the computer cable to **24cm length**.  
- **Solder** the computer cable to the **12V servo pin**, ensuring correct polarity.  

<img src="../media/1_power_module_modified.avif" alt="Modified power module" width="400">

---

## 2. Brushless Motor Modification

### Materials

<img src="../media/1_brushless_motor_exploded.avif" alt="Exploded view of brushless motor components" width="400">

| Part Name | Quantity | Description | Reference |
|:-|:-:|:-|:-:|
| TMotor F90-1300KV | 6 | | [TMotor](https://store.tmotor.com/goods.php?id=1064) |
| Banana Plug | 18 | 3.5 mm, male | [RC Innovations](https://rc-innovations.es/shop/con00000438-conector-banana-3-5mm-tipo-tmotor-pareja-18644?search=conector+banana) |

For the brushless motor, you'll need to solder the correct connector to connect it to the ESC. The existing cable is longer than necessary, so it will be trimmed. The leftover pieces from the motor's cable will be soldered to the ESC.

### Steps
- **Trim** the phase cables by about **5cm**.
  > :warning: Retain the leftover cables for the ESCs.
- **Solder** the male banana connectors to the phase cables. Use the hole on the side to easely melt the iron paste between the wire and the connector with the solder iron.
- **Add** heat shrink tubing around the connectors to insulate the soldered joints.

- **Repeat** the steps for all 6 brushless motors.

<img src="../media/1_motor_modified.avif" alt="Modified motor" width="400">

---

## 3. ESC Modification
<img src="../media/esc.png" alt="Modified ESC" width="400">

### Materials
| Part Name | Quantity | Description | Reference |
|:-|:-:|:-|:-:|
| TMotor F35A 6s | 6 | | [TMotor](https://store.tmotor.com/goods.php?id=1176) |
| Red Power Cable | 6 | 30cm Silicone 16 AWG cable in Red | [RC Innovations](https://rc-innovations.es/shop/Cable-silicona-16AWG-Rojo-1-metro-amass) |
| Black Power Cable | 6 | 30cm Silicone 16 AWG cable in Black | [RC Innovations](https://rc-innovations.es/shop/Cable-silicona-16AWG-Negro-1-metro-amass) |
| White Servo Cable | 6 | 30cm Silicone 26 AWG cable in White | [RC Innovations](https://rc-innovations.es/shop/Cable-de-silicona-26AWG-blanco-1-metro) |
| Black Servo Cable | 6 | 30cm Silicone 26 AWG cable in Black | [RC Innovations](https://rc-innovations.es/shop/cable-de-silicona-26-awg-negro-1-metro) |
| Banana Plug | 18 | 3.5 mm, female | [RC Innovations](https://rc-innovations.es/shop/con00000438-conector-banana-3-5mm-tipo-tmotor-pareja-18644?search=conector+banana) |
| XT30 Connector | 6 | Male | [~RC Innovations~](https://rc-innovations.es/shop/amass-conector-xt30-macho-xt30u-m) |
| Servo Connector | 6 | Female | [RC Innovations](https://rc-innovations.es/shop/Conector-servo-Futaba-hembra) |

The ESC connects to three components: the brushless motor (via phase cables), the power module (via power cables), and the Pixhawk (via servo cables). You must prepare all three connections for the ESC to function.

### Steps
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

---

[Next → Airframe Assembly](2_airframe_assembly.md)