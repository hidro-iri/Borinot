# Environment Setup

## Part 1: Flying Area Setup
1. Put the net
2. Put the safety glass in front of the desks (should not be covered by the net)
  - Top view od the lab with glass position, tables, little path [for manipulation] and net
3. Move the two table for borinot manipulation
4. Install power supply + computer
5. **FREE THE FLYING AREA** (SHOW IT ON THE PICTURE)


## Part 2: Optitrack Setup
- Already documentation for the calibration in `iri_optitrack_how_to` (find the link)
- + add info about
  - pose of the origin (top view of the lab)
  - pose of Borinot when creating the "solid" (top view )
    - Put the drone on top of a table for all the cameras to detect it
  - the name convention `borinot_fur_ot`
  - origin and offset of the "imu center" (check error per markers + untrack markers)
    - origin : intern / down left marker 
    - x : 62.9
    - y : 29.0
    - z : 84.9
- steam (in streaming panel)
  - check IP
  - activate bradcast
  - activate vrpn












# [Preflight safety checklist](preflight.md)



Before each flight, it's important to perform a series of checks to ensure that the UAM is safe to operate. Follow the procedures outlined in the [preflight.md](preflight.md) file to complete these checks.

### [Optitrack fusion](optitrack.md)

The [optitrack.md](optitrack.md) file provides a procedure for fusing the position of the OptiTrack system with the PX4's EKF2 module.