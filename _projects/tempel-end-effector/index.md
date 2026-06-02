---
layout: post
title: COMETS 2025 “Tempel” Differential End Effector Subsystem
description: Designed a competition robotics end effector featuring an integrated differential gearbox for independent wrist and intake wheel control. Iterative development focused on perfecting game piece manipulation, weight distribution, and cross-system integration.
skills: 
- SolidWorks
- Differential Gearbox Design
main-image: /tempel_main.png 
---

---
## Design Overview

### Objective:
Design and manufacture a compact end effector capable of independently rotating a wrist mechanism and controlling intake flywheel spin.

### Key Components:
- Differential bevel gearbox
- Pulley-driven power transmission
- Aluminum tubes and plastic plates
- Neo motor mounting plates
- Through bore encoder attachment

### Challenges and Iteration:
- Intake geometry underwent multiple redesigns to optimize contact with cylindrical game pieces
- Transitioning from four intake wheels to three improved game piece grip stability
- Implementing a modular assembly approach was necessary for quick repair in competition setting
- Balancing rigidity, packaging constraints, and rotational freedom required several system revisions

### Final Output:
The completed end effector operated as a highly effective and dependable subsystem, providing stable game piece control, reliable wrist positioning, and consistent performance throughout competition use.

---
## Component Breakdowns

### Differential Bevel Gearbox:
The custom differential bevel gearbox transfers energy from two powered shafts into a compact mechanism capable of independently controlling wrist rotation and intake wheel spin. This gearbox was the defining feature of the end effector, allowing multiple motions to be integrated into a single assembly while maintaining precise control. The gearbox was manufactured using a combination of CNC-machined components, bearings, metal gears, and custom 3D-printed parts to balance strength, weight, and packaging constraints.

{% include image-gallery.html images="tempel_gearbox.png" height="300" %}
<span style="font-size: 10px"> </span>

### Pulley-Driven Power Transmission:
A series of pulley systems transfers rotational power through long shafts and into the gearbox and wheel drive mechanisms. This arrangement enabled power to be routed efficiently through the narrow geometry of the arm while keeping the drivetrain compact and serviceable. The pulley-driven layout also provided flexibility in tuning gear ratios during the iteration process.

{% include image-gallery.html images="tempel_pulleys.png" height="300" %}
<span style="font-size: 10px"> </span>

### Aluminum Tubes and Plastic Plates:
The structure of the end effector was built primarily from lightweight aluminum tubing and machined polycarbonate side plates to minimize weight while maintaining rigidity. The geometry of the side plates underwent multiple iterations as the intake was tested. Additional custom 3D-printed components were incorporated throughout the assembly to reduce machining complexity.

{% include image-gallery.html images="tempel_plates.png" height="300" %}
<span style="font-size: 10px"> </span>

### Neo Motor Mounting:
Both Neo motors were intentionally positioned on the opposite side of the arm’s axis of rotation in order to evenly distribute weight across the subsystem and minimize torque loading on the pivot. This design choice improved the arm’s responsiveness and reduced the mechanical demand on the separate arm-rotation mechanism.

{% include image-gallery.html images="tempel_neos.png" height="300" %}
<span style="font-size: 10px"> </span>

### Through Bore Encoder Attachment:
A through bore encoder mounted on the central arm tube provides accurate feedback on the rotational position of the wrist for the robot’s control system. The encoder assembly was designed with the same gear ratio as the wrist drive to ensure precise positional tracking throughout operation.

{% include image-gallery.html images="tempel_encoder.png" height="300" %}
<span style="font-size: 10px"> </span>
