# Component Preparation Guide

Some components require modifications before assembling. This guide covers adjustments needed for the power module, brushless motors, and ESCs.

---

## Part 1: Power Module Modification

The Power Module distributes power to all components (computer, motors, arm, flight controller) and monitors battery status via Pixhawk.

### Materials

<img src="../media/1_power_module_materials.avif" alt="materials for power module modification" width="350" align="center">

> **Top view list**
> - computer cable (`#8`)
> - power module (`#1`)
> - masterboard power cable (`#9`) with JST connectors (`#10`)
> - EC5 connector (`#2`)
> - XT30-F connector (`#3`)
> - diode (`#5`)
> - XT30-M connector (`#4`)
> - red (`#6`) and black (`#7`) power cables

| ID    | Part Name             | Qty | Description                          | Location | Reference             |
|-------|-----------------------|-----|--------------------------------------|----------|-----------------------|
| `#1`  | PM03D Power Module    | 1   | Base unit                            | HS-      | Holybro               |
| `#2`  | EC5-M Connector       | 1   | Male battery connector               | HS-      | TME                   |
| `#3`  | XT30-F Connector      | 1   | Female power connector               | HS-      | RC Innovations        |
| `#4`  | XT30-M Connector      | 1   | Male power connector                 | HS-      | RC Innovations        |
| `#5`  | Diode                 | 1   | BQ30TB 45B714                        | HS-      | -                     |
| `#6`  | Red Power Cable       | 2   | 15cm 16AWG Silicon                   | HS-      | RC Innovations        |
| `#7`  | Black Power Cable     | 2   | 15cm 16AWG Silicon                   | HS-      | RC Innovations        |
| `#8`  | Computer Cable        | 1   | 24cm barrel plug (5.5×2.5mm)         | HS-      | Amazon                |
| `#9`  | Masterboard Cable     | 1   | 17cm line                            | HS-      | ODRI                  |
| `#10` | Connector JST         | 1   | Male                                 | HS-      | RC Innovations        |

### Steps

<img src="../media/1_power_module_step_1a.avif" alt="Step 1A: Unsoldering original XT60 connector from PM03D (Component #1)" width="350"> 
<img src="../media/1_power_module_step_1b.avif" alt="Step 1B: EC5-M connector installed on power module (Component #2)" width="350">

> **Battery Cable Modification**  
> Left: Original XT60 configuration | Right: Modified EC5 connector installation

1. **Unsolder** the capacitor and battery cable from the board (`#1`).
2. **Replace** the battery cable's connector from XT60 to EC5 (`#2`).
   
   > :warning: Do not cut the cable to remove the XT60.  
   > :information_source: Apply pressure when inserting EC5 terminals into housing.

3. **Resolder** the capacitor and battery cable so they point **inward** on the board.

---

<img src="../media/1_power_module_step_2a.avif" alt="Step 4-7: Hot-swap cable assembly - Diode (#5) and XT30-M (#4) before heat shrink" height="350"> 
<img src="../media/1_power_module_step_2b.avif" alt="Step 4-7: Hot-swap cable completed - Heat shrink applied to XT30-M (#4) connections" height="350">

> **Hot-Swap Cable Assembly**  
> Left: Pre-sealed assembly showing diode (#5) and XT30-M (#4) connections | Right: Finished cable with insulated joints

4. **Bend** the diode's (`#5`) anode (right leg) to connect with the positive terminal of the XT30-M connector (`#4`) and **solder**.
5. **Solder** the diode's cathode (left leg) to the positive power cable (`#6`).
6. **Solder** the negative power cable (`#7`) to the negative terminal of the XT30-M connector.
7. **Add** heat shrink tubing over the connectors and **heat** to seal.  
   > :information_source: This becomes the **hot-swap cable** - compare your result with right image above.
8. **Solder** the hot-swap cable to the battery cable location, keeping the same orientation (**See final picture of the part**).

---

<img src="../media/1_power_module_step_3a.avif" alt="Step 9-10: Microdriver cable components - XT30-M (#4), red (#6) & black (#7) cables unsoldered" width="350"> 
<img src="../media/1_power_module_step_3b.avif" alt="Step 9-10: Completed microdriver cable - XT30-M (#4) with heat shrunk connections" width="350">

> **Microdriver Cable Assembly**  
> Left: Preparation stage | Right: Finished assembly  
> Components: XT30-F connector (`#5`), red 16AWG (`#6`), black 16AWG (`#7`)

9. **Solder** both power cables to XT30-F connector (`#5`):
   - Red (`#6`) → Positive terminal
   - Black (`#7`) → Negative terminal

10. **Add** heat shrink tubing and **seal** connections.  
    > :information_source: Now referred to as **microdriver cable** - compare with right image.
11. **Solder** microdriver cable to board:
   - Red (`#6`) → B+ pad
   - Black (`#7`) → GND pad  
   > :warning: Apply heat shrink over connector before use (as shown right).
---

<img src="../media/1_power_module_step_4.avif" alt="Masterboard components" width="350">

> **Top view: Components for masterboard cable (from right to left: masterboard power cable, JST male connector, JST female connector)**

12. **Cut** the masterboard power cable in half.
13. **Crimp** JST connector onto each cable.
    > :warning: Be sure to put the connector the correct way to ensure positive-to-positive alignment.

14. **Use** the connector-bearing cable for the [flying arm assembly](6_flying_arm_assembly.md) and the other as the **masterboard cable**.
15. **Solder** the masterboard cable to the **5V com pin**, ensuring proper polarity (black cable to ground, green cable to 5V).
    > :information_source: Add heat shrink over exposed pins for safety.

---

<img src="../media/1_power_module_step_5.avif" alt="Computer components" width="350">

> **Close view: VDD jumper pins (middle left) and computer cable at servo pin (lower right)**

16. **Set VDD to 12V** using the jumper configuration.
17. **Cut** the computer cable to a **24cm length**.
18. **Solder** the computer cable to the **VDD servo pin**, maintaining correct polarity.
    > :information_source: Cover solder joints with heat shrink tubing.

---

<img src="../media/1_power_module_modified.avif" alt="Modified power module" width="350">

> **Top view: Final modified power module**

---

## Part 2: Brushless Motor and ESC Modification

In this part you’ll modify both the brushless motors and the ESCs. Follow the steps closely to ensure proper electrical connections and maintain correct polarity.

### Materials

<img src="../media/1_brushless_motor_exploded.avif" alt="Exploded view of brushless motor components" width="350">

> **Top view: Components for motor and ESC modification (from top to bottom, left to right: servo connector, ESC, motor, servo pins, power cables, banana plug, XT30-M connector, signal cables)**

| Part Name             | Quantity | Description                          | Reference                                                                                                    |
|-----------------------|:--------:|--------------------------------------|--------------------------------------------------------------------------------------------------------------|
| TMotor F90-1300KV     | 6        | Brushless motor                      | [TMotor](https://store.tmotor.com/goods.php?id=1064)                                                         |
| Banana Plug (male)    | 18       | 3.5 mm, male                         | [RC Innovations](https://rc-innovations.es/shop/con00000438-conector-banana-3-5mm-tipo-tmotor-pareja-18644)  |
| TMotor F35A 6s        | 6        | ESC                                  | [TMotor](https://store.tmotor.com/goods.php?id=1176)                                                         |
| Red Power Cable       | 6        | 30cm Silicone 16 AWG cable in Red     | [RC Innovations](https://rc-innovations.es/shop/Cable-silicona-16AWG-Rojo-1-metro-amass)                     |
| Black Power Cable     | 6        | 30cm Silicone 16 AWG cable in Black   | [RC Innovations](https://rc-innovations.es/shop/Cable-silicona-16AWG-Negro-1-metro-amass)                    |
| White Servo Cable     | 6        | 30cm Silicone 26 AWG cable in White   | [RC Innovations](https://rc-innovations.es/shop/Cable-de-silicona-26AWG-blanco-1-metro)                      |
| Black Servo Cable     | 6        | 30cm Silicone 26 AWG cable in Black   | [RC Innovations](https://rc-innovations.es/shop/cable-de-silicona-26-awg-negro-1-metro)                      |
| Banana Plug (female)  | 18       | 3.5 mm, female                       | [RC Innovations](https://rc-innovations.es/shop/con00000438-conector-banana-3-5mm-tipo-tmotor-pareja-18644)  |
| XT30 Connector (male) | 6        | XT30 male connector                  | [RC Innovations](https://rc-innovations.es/shop/amass-conector-xt30-macho-xt30u-m)                           |
| Servo Connector       | 6        | Female                               | [RC Innovations](https://rc-innovations.es/shop/Conector-servo-Futaba-hembra)                                |

### Steps

#### Brushless Motor Modification

<img src="../media/1_motor_step_1.avif" alt="Brushless motor modification" width="350">

> **Top view: Motor and banana plugs (from left to right)**

1. **Trim** the phase cables by about **5cm**.  
   > :warning: Retain the trimmed segments for the ESC modification.
2. **Solder** the male banana plugs to the trimmed phase cables.  
   > :information_source: Use the connector’s side hole to help evenly melt the solder paste.
3. **Add** heat shrink tubing around the connectors to insulate the soldered joints.
4. **Repeat** these steps for all 6 brushless motors.

---

<img src="../media/1_motor_modified.avif" alt="Modified brushless motor" width="350">

> **Close view: Finalized motor**

#### ESC Modification

<img src="../media/1_esc_step_1.avif" alt="ESC modification" width="350">

> **Close view: ESC faces – Left/Middle ones show pads labeled `–`, `S`, and `T` for signal cables at the bottom left. Right one shows power cable pads at the top; displays phase cable pads at the bottom**

5. **Solder** 5cm of the leftover phase cables from the motors to the ESC’s phase pads.
6. **Attach** the female banana plugs to these phase cables and **add** heat shrink tubing over the connections before heating to seal.
7. **Solder** 30cm power cables to the ESC’s power pads.  
   > :information_source: Connect the red cable to the positive (`+`) pad and the black cable to the negative (`–`) pad.
8. **Slide** heat shrink tubing onto both power cables (do not heat yet).
9. **Solder** the XT30 male connectors to the ends of the power cables.  
   > :warning: Double-check polarity before sealing.
10. **Heat** the tubing to secure the connections.

---

<img src="../media/esc_servo_crimp.jpg" alt="ESC servo connector orientation" width="250">

11. **Solder** 30cm servo cables to the ESC’s servo pads.  
    > :information_source: Attach the white cable to the signal (S) pad and the black cable to the ground (–) pad.
12. **Crimp** the wires and attach the servo connectors.  
    > :warning: Orientation matters - white wire must align with signal (S) pad position.  
    > Match connector notch with ESC's plastic alignment tab.

13. **Repeat** the entire ESC modification process for all 6 ESCs.

---

<img src="../media/1_esc_modified.avif" alt="Modified ESC" width="350">

> **Top view: Finalized modified ESC**


---
[Next → Airframe Assembly](2_airframe_assembly.md)
