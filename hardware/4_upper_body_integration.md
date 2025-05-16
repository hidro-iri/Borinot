# Upper Body Integration

## 3D part 

### Materials

- 3d parts (spacers)
- nuts M3 (x8)

### Steps

1. clean plastic
2. put nuts

## Airframe Mounting

### Materials

- Main Body
- Airframe
- 3D parts

### steps

1. Place the main body on top of the airframe keeping the fronts align.
> :information_source: each CF tube should fit inside the CFT slots.  
> ⚠️  if one triangle does not fit, place properly two tubes and reassemble the two others motor cases to make the third bare fits.  
2. Put the medium spacer between the differents carbon fiber tubes and tight them with fasterner.
> ⚠️  The slots should be facing out.  
> :information_source: The spacer is place at the intersections of the carbon fibers tube. (seeing from the top)  
> :information_source: use the main body's inside cavity to hide the head of the fasteners.
> ⚠️  be careful to not fastern cables in it.
> :Cut the oer part of the fasterner. 

3. Put all the other spacers where they should go.
> ⚠️  The slots should be facing out.  
> :information_source: The spacer is place at the intersections of the carbon fibers tube. (seeing from the top)  
> :information_source: The more distance between two tubes, the bigger the spacers


4. For each landing gear interface, put it in place and tight it using fasterner.
> ⚠️  The slots should be facing out.  
> :info_source: The interface should fit just below the spacer.
> :information_source: use the main body's inside cavity to hide the head of the fasteners.
> ⚠️  be careful to not fastern cables in it.
> :Cut the oer part of the fasterner. 



- 2. Put one spacer between the differents carbon fiber tubes (start with the medium ones, then the big ones, then the small one).

- smaller between top and middle
- medium between middle and bottom
- large between top and bottom

- 3. if the spacer if touching the lower bares (small and big ones), put the associate landing gear interface below the spacer

- 4. Tight the airframe to the main body where the spacer is using fasteners

- 5. repeat steps 2 to 4 for each spacer.


## Upper Body Routing

> ⚠️  Patience is key.

### Materials

- USB-C cable
- receiver cable
- spiral attach

### steps

> Put a top view of the frame with the bar colored with the type of cable that should be passing through.

Motors connected to the Power module back : 1, 4, 6
Motors connected to the Power module front : 2, 3, 5

- signal cable goes to the bare that put them close to the back of the Pixhawk

1. Follow the routing schematic. (picture showing on which should pass each cable.)
    > Signal and Power cables should be twisted properly to ensure 
2. Continue with the signal cables.
3. Start by the power cables
4. Connect the signal cable following the [Hexarotor X airframe reference](https://docs.px4.io/main/en/airframes/airframe_reference.html#hexarotor-x). 
    > :information_source: To identify the proper cable (i.e cable number i) between all, proceed as follow: maintain the signal cable i on the motor side (as you are sure it is the good one), on the pixhawk side, pull each cable one by one, if you feel some force on the motor side, you have the good one!
 

4. Finish with the other cables.
    - From Pixhawk : ethernet !!! , power (should be already connected at main body assembly), serial bus (usb-c) [also to pixhawk] !!!,
    - From the computer : ethernet extender !!!, wifi antenna,
    - From power module : microcontroller cable, masterboard cable,
    - From radio receiver : two antennas,  radio receiver, 

5. Put the spiral to maintain the cable with the frame.
    - cable should pass below the tube
    - `Assure that the cables are properly twisted!!!`
    - Radio antenna should be put above the tube

6. 
---

| [Top of page](#upper-body-integration) | [Back to Hardware Building Instructions](README.md) | [Back to Borinot HOME](../README.md) | [Next → Landing Gear Assembly](5_landing_gear_assembly.md) |
| --- | --- | --- | --- |