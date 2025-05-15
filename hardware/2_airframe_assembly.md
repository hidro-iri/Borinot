# Airframe Assembly Guide

The airframe is the structure that houses and maintains the motors in their respective positions. This guide covers the assembly procedure for the airframe.

---

## Part 1: Motor Case Preparation

The Motor Case holds both the motor and the carbon fiber tubes together. It also houses the esc and the Optitrack markers.

### Materials

<img src="../media/2_motor_case_exploded.avif" alt="Exploded view of Motor Case" width="350">

> **Exploded View: Motor Case components (all 3D printed parts)**

| Part Name             | Quantity | Description                   | Reference                                                              |
|-----------------------|:--------:|-------------------------------|------------------------------------------------------------------------|
| Motor Cases           | 6        | 3D parts – Motor Holder       | [CAD](CAD/platform/)                                                   |
| M4 Marker             | 6        | 14 mm M4                      | [Optitrack](https://optitrack.com/accessories/markers/#mcm-14.0-m4-10) |
| M4 Nuts               | 6        | M4                            |                                                                        |
| M4 Screws             | 6        | M4x10mm Nylon                 |                                                                        |
| M3 Inserts            | 12       | M3                            |                                                                        |

### Steps

1. **Clean** all Motor Case components, ensuring removal of any support material inside the tube holder.  
   > ⚠️  Use a drill if anomalies are found inside the tube holder.

<img src="../media/2_motor_case_step_1.avif" alt="Before marker assembly" width="350"> <img src="../media/2_motor_case_step_1b.avif" alt="Before marker assembly" width="350">

> **Side view:** middle part before and after installing the marker

2. **Assemble** the marker (M4 nut + M4 nylon screw + M4 marker) according to the **Motor ID**.  
   > ⚠️  The faces of the middle part are not symmetric. Test alignement with the top and bottom parts so find the correct orientation.

   > :information_source: Each Motor Case is identified using the [Hexarotor X airframe reference](https://docs.px4.io/main/en/airframes/airframe_reference.html#hexarotor-x) ID.

<img src="../media/2_motor_case_marker.avif" alt="Marker position" width="350">

> **Side view** Marker position

| Motor ID | Marker Position |
|:--------:|-----------------|
| 1        | Bottom Right    |
| 2        | Top Right       |
| 3        | Top Left        |
| 4        | Bottom Left     |
| 5        | Top Right       |
| 6        | Bottom Right    |

<img src="../media/2_motor_case_step_2.avif" alt="Before asserts on bottom" width="350"> <img src="../media/2_motor_case_step_2b.avif" alt="After asserts on bottom" width="350">

> **Side view:** Bottom part before and after inserting asserts

3. **Install** two inserts on the bottom part.

<img src="../media/2_motor_case_step_3.avif" alt="Cover assembly before" width="350"> <img src="../media/2_motor_case_step_3b.avif" alt="Cover assembly after" width="350">

> **Side view:** Cover before and after assembling the cover

4. **Assemble** the different piece composing the cover.

5. **Repeat** these steps for all 6 Motor Cases.


<img src="../media/2_motor_case_prepared.avif" alt="Motor case prepared" width="350">

> **Side view:** Motor case prepared.

---

## Part 2: Frame Assembly

The frame is composed of two intersecting triangles. Each motor case is a vertex and each carbon fiber tube a edge.

### Materials

| Part Name             | Quantity | Description                   | Reference                                                              |
|-----------------------|:--------:|-------------------------------|------------------------------------------------------------------------|
| Carbon Fiber Tubes    | 6        | ø8mm x 352.5mm, Round Checked | [McMaster](https://www.mcmaster.com/products/carbon-fiber-tubing/) |
| O-ring Seals          | 24       | ø8 mm                         | [TheORingStore](https://www.theoringstore.com/store/)              |
| M3x30mm Screws        | 24       | M3x30mm                       |                                                                    |
| M3x05mm Screws        | 12       | M3x05mm                       |                                                                    |
| Motors and ESCs       | 6        |                               | [Component Preparation](1_component_preparation.md)                |




<img src="../media/airframe.png" alt="Assembled airframe top view" width="350">

> **`Assembled Airframe:`** Top view of the assembled airframe

| Motor ID | Left Position | Right Position |
|:--------:|---------------|----------------|
| 1        | Middle        | Top            |
| 2        | Middle        | Top            |
| 3        | Top           | Bottom         |
| 4        | Top           | Bottom         |
| 5        | Bottom        | Middle         |
| 6        | Bottom        | Middle         |

### Steps

<img src="../media/airframe_assembly_1.png" alt="Motor Case 3 assembly" width="350">

> **`Assembly Step 1:`** Top view of Motor Case 3 assembly

1. **Combine Motor Cases:** Assemble the top, middle, and bottom parts of each Motor Case.  
   > :information_source: Ensure the O-rings are snugly fitted.
2. **Attach Tubes:** Insert Carbon Fiber Tubes into the tube holders of the Motor Cases and secure them with 4 M3x30mm screws.  
   > ⚠️  Refer to the table above for tube positioning.
3. **Add Tube Accessories:** For each tube, slide on two O-rings and a 7cm length of heat shrink tubing on both ends.
4. **Assemble Triangles:**  
   - Assemble Motor Cases 1, 3, and 6 to form the first triangle.  
   - Assemble Motor Cases 4 and 5 to form the second triangle.
5. **Merge Triangles:** Merge the two triangles before sealing the final Motor Case (Motor Case 2).
6. **Finalize Frame:** Complete the assembly by installing Motor Case 2.

<img src="../media/airframe_assembly_4.png" alt="Frame before closing" width="350">

> **`Frame Finalization:`** Top view of the airframe before closing

---

## Part 3: Finalizing Assembly

With the frame assembled, install the ESCs and connect them to the motors. Route the ESC cables through the designated heat shrink tubing for stability and a clean finish.

### Materials

<img src="../media/airframe.png" alt="Assembled airframe" width="350">

> **`Reference:`** Assembled airframe used as a reference for ESC installation

### Steps

1. **Install ESCs:** Position the ESC within the bottom section of each Motor Case and connect it to its corresponding motor.
2. **Mount Covers:** Attach the cover onto each Motor Case using 2 M3x5mm screws.
3. **Route Cables:** Route the ESC cables through the designated heat shrink tubing on the Carbon Fiber Tubes.  
   > ⚠️  Ensure cables are routed according to the assembly guidelines.
4. **Repeat:** Complete these steps for all 6 Motor Cases.

---

[Next → Main Body Assembly](3_main_body_assembly.md)
