# Components List

Before beginning assembly, ensure you have all necessary components on hand. This list is organized into categories for ease of reference.

## Upper Part

<!-- Put Picture of all the piece of the upper part -->
<!-- Plus comment of the picture -->

| Part Name             | Quantity | Description                          | Reference                                                                                   |
|-----------------------|----------|--------------------------------------|---------------------------------------------------------------------------------------------|
| PM03D Power Module    | 1        | Base unit                            | [Holybro](https://holybro.com/products/pm03d-power-module)                                  |
| EC5-M Connector       | 1        | Male battery connector               | [TME](https://www.tme.eu/es/en/details/ec5-m/dc-power-connectors/amass/)                    |
| XT30-F Connector      | 1        | Female power connector               | [RC Innovations](https://rc-innovations.es/shop/amass-conector-xt30-hembra-xt30u-h)         |
| XT30-M Connector      | 1        | Male power connector                 | [RC Innovations](https://rc-innovations.es/shop/amass-conector-xt30-macho-xt30u-m)          |
| Diode                 | 1        |                                      | `BQ30TB 45B714`                                                                             |
| Red Power Cable       | 2        | 15cm 16AWG (VCC)                     | [RC Innovations](https://rc-innovations.es/shop/Cable-silicona-16AWG-Rojo-1-metro-amass)    |
| Black Power Cable     | 2        | 15cm 16AWG (GND)                     | [RC Innovations](https://rc-innovations.es/shop/cable-de-silicona-26-awg-negro-1-metro)     |
| Computer Cable        | 1        | 24cm barrel plug (5.5×2.5mm)         | [Amazon](https://www.amazon.com/Generic-5-5mm-2-5mm-Right-Pigtail/dp/B07H38LNPD)            |
| Masterboard Cable     | 1        | 17cm line                            |                                                                                             |
| Connector JST         | 1        | Male                                 |                                                                                             |


| Part Name | Quantity | Type | Assembly Reference |
|:-|:-:|:-:|:-|
| [Motor Cases](CAD/motor_case/) | 6 | 3D part | [Airframe Assembly](building_instructions.md#airframe-assembly) |
| [Body Case](CAD/body_case/) | 1 | 3D part | [Body Assembly](building_instructions.md#body-assembly) |
| [Landing Gear](CAD/landing_gear/) | 1 | | [Landing Gear Assembly](building_instructions.md#landing-gear-assembly) |
| [Controller Case](CAD/controller_case/) | 1 | | [Controller Assembly](building_instructions.md#controller-assembly) |
| [2DOF Flying Arm](CAD/flying_arm/) | 1 | | [Flying Arm Assembly](building_instructions.md#flying-arm-assembly) |
| [TMotor F90-1300KV](https://store.tmotor.com/goods.php?id=1064) | 6 | | [Airframe Assembly](building_instructions.md#airframe-assembly) |
| [TMotor F35A 6s](https://store.tmotor.com/goods.php?id=1176) | 6 | | [Airframe Assembly](building_instructions.md#airframe-assembly) |
| [NUC i7](https://ark.intel.com/content/www/us/en/ark/products/series/217835/intel-nuc-kit-with-12th-generation-intel-core-processors.html) | 1 | | [Body Assembly](building_instructions.md#body-assembly) |
| [PixHawk5](https://docs.px4.io/main/en/flight_controller/pixhawk5x.html) | 1 | | [Body Assembly](building_instructions.md#body-assembly) |
| ø**...**mm O-ring Seals | 24 | | [Airframe Assembly](building_instructions.md#airframe-assembly) | <!--Mechanical Components-->
| ø20mm O-ring Seals | 12 | | [Landing Gear Assembly](building_instructions.md#landing-gear-assembly) |
| M3x5mm Screws | 12 | | [Airframe Assembly](building_instructions.md#airframe-assembly) |
| M3x10mm Screws | 8 | | [Landing Gear Assembly](building_instructions.md#landing-gear-assembly) |
| M3x10mm Nylon Screws | 6 | | [Airframe Assembly](building_instructions.md#airframe-assembly) |
| M3x16mm Screws | 8 | | [Landing Gear Assembly](building_instructions.md#landing-gear-assembly) |
| M3x30mm Screws | 24 | | [Airframe Assembly](building_instructions.md#airframe-assembly) |
| M4 Nuts | 6 | | [Airframe Assembly](building_instructions.md#airframe-assembly) |
| M3 Nuts | 16 | | [Landing Gear Assembly](building_instructions.md#landing-gear-assembly) |
| M3 Inserts | 12 | | [Airframe Assembly](building_instructions.md#airframe-assembly) |
| Cable Ties | 6 | | [Body Assembly](building_instructions.md#body-assembly) |
| ø8mmx110.0mm Carbon Fiber Round Tubes | 4 | | [Landing Gear Assembly](building_instructions.md#landing-gear-assembly) |
| ø8mmx170.0mm Carbon Fiber Round Tubes | 2 | | [Landing Gear Assembly](building_instructions.md#landing-gear-assembly) |
| ø8mmx300.0mm Carbon Fiber Round Tubes | 2 | | [Landing Gear Assembly](building_instructions.md#landing-gear-assembly) |
| ø8mmx352.5mm Carbon Fiber Round Tubes | 6 | | [Airframe Assembly](building_instructions.md#airframe-assembly) |
| [Markers](https://optitrack.com/accessories/markers/#mcm-14.0-m4-10) | 11 | | [Airframe Assembly](building_instructions.md#airframe-assembly) & [Body Assembly](building_instructions.md#body-assembly)|


## Lower Part


## Electronics

- **Computer:** Intel [NUC i7](https://ark.intel.com/content/www/us/en/ark/products/series/217835/intel-nuc-kit-with-12th-generation-intel-core-processors.html)
- **Flight Controller:** [PixHawk5](https://docs.px4.io/main/en/flight_controller/pixhawk5x.html)
- **Power Module:** [PM03D Power Module](https://holybro.com/collections/power-modules-pdbs/products/pm03d-power-module)
- **ESC:** [TMotor F35A 6s](https://store.tmotor.com/goods.php?id=1176)
- **Control Board:** [Master board](https://github.com/open-dynamic-robot-initiative/master-board#master-board) from [ODRI](https://github.com/open-dynamic-robot-initiative)
- **Driver:** [Micro Driver](https://github.com/open-dynamic-robot-initiative/open_robot_actuator_hardware/tree/master/electronics/micro_driver_electronics) from ODRI
- **Actuator:** [Actuator Module](https://github.com/open-dynamic-robot-initiative/open_robot_actuator_hardware/blob/master/mechanics/actuator_module_v1/README.md) from ODRI

## 3D Printed Parts

- **Motor Case:** Comprising a *top*, two *middles*, a *bottom*, and a *cache*.
- **Body Case:** Consisting of a *top*, a *crown*, a *bottom*, and two sizes of *tube holders (S,M, and L)*.
- **Landing Gear:** Including four *attachments*, four *feet*, and four *pawns*.
- **Controller Case:** Consisting of a *top* and a *bottom*.
- **2DOF Flying Arm**

## Bill of Materials - Borinot

| Part Name | Quantity | Comments | Assembly Reference |
|:-|:-:|:-:|:-|
| [Motor Cases](CAD/motor_case/) | 6 | | [Airframe Assembly](building_instructions.md#airframe-assembly) |
| [Body Case](CAD/body_case/) | 1 | | [Body Assembly](building_instructions.md#body-assembly) |
| [Landing Gear](CAD/landing_gear/) | 1 | | [Landing Gear Assembly](building_instructions.md#landing-gear-assembly) |
| [Controller Case](CAD/controller_case/) | 1 | | [Controller Assembly](building_instructions.md#controller-assembly) |
| [2DOF Flying Arm](CAD/flying_arm/) | 1 | | [Flying Arm Assembly](building_instructions.md#flying-arm-assembly) |
| [TMotor F90-1300KV](https://store.tmotor.com/goods.php?id=1064) | 6 | | [Airframe Assembly](building_instructions.md#airframe-assembly) |
| [TMotor F35A 6s](https://store.tmotor.com/goods.php?id=1176) | 6 | | [Airframe Assembly](building_instructions.md#airframe-assembly) |
| [NUC i7](https://ark.intel.com/content/www/us/en/ark/products/series/217835/intel-nuc-kit-with-12th-generation-intel-core-processors.html) | 1 | | [Body Assembly](building_instructions.md#body-assembly) |
| [PixHawk5](https://docs.px4.io/main/en/flight_controller/pixhawk5x.html) | 1 | | [Body Assembly](building_instructions.md#body-assembly) |
| ø**...**mm O-ring Seals | 24 | | [Airframe Assembly](building_instructions.md#airframe-assembly) | <!--Mechanical Components-->
| ø20mm O-ring Seals | 12 | | [Landing Gear Assembly](building_instructions.md#landing-gear-assembly) |
| M3x5mm Screws | 12 | | [Airframe Assembly](building_instructions.md#airframe-assembly) |
| M3x10mm Screws | 8 | | [Landing Gear Assembly](building_instructions.md#landing-gear-assembly) |
| M3x10mm Nylon Screws | 6 | | [Airframe Assembly](building_instructions.md#airframe-assembly) |
| M3x16mm Screws | 8 | | [Landing Gear Assembly](building_instructions.md#landing-gear-assembly) |
| M3x30mm Screws | 24 | | [Airframe Assembly](building_instructions.md#airframe-assembly) |
| M4 Nuts | 6 | | [Airframe Assembly](building_instructions.md#airframe-assembly) |
| M3 Nuts | 16 | | [Landing Gear Assembly](building_instructions.md#landing-gear-assembly) |
| M3 Inserts | 12 | | [Airframe Assembly](building_instructions.md#airframe-assembly) |
| Cable Ties | 6 | | [Body Assembly](building_instructions.md#body-assembly) |
| ø8mmx110.0mm Carbon Fiber Round Tubes | 4 | | [Landing Gear Assembly](building_instructions.md#landing-gear-assembly) |
| ø8mmx170.0mm Carbon Fiber Round Tubes | 2 | | [Landing Gear Assembly](building_instructions.md#landing-gear-assembly) |
| ø8mmx300.0mm Carbon Fiber Round Tubes | 2 | | [Landing Gear Assembly](building_instructions.md#landing-gear-assembly) |
| ø8mmx352.5mm Carbon Fiber Round Tubes | 6 | | [Airframe Assembly](building_instructions.md#airframe-assembly) |
| [Markers](https://optitrack.com/accessories/markers/#mcm-14.0-m4-10) | 11 | | [Airframe Assembly](building_instructions.md#airframe-assembly) & [Body Assembly](building_instructions.md#body-assembly)|
