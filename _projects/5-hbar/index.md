---
layout: post
title: HBAR Eigenmode Characterization & Device Design
description: Developed an automated COMSOL-MATLAB workflow for the design and characterization of High Overtone Bulk Acoustic Resonator (HBAR) devices. The workflow identifies HBAR modes through Hermite-Gaussian distribution fitting and explores the effects of device geometry on resonant performance.
skills: 
- MATLAB
- COMSOL
- LiveLink
main-image: /vaisala_cover.png 
---

---
## Design Overview

### Objective:
Design and manufacture a durable pivot mechanism for controlling the angle of the robot’s shooting deck capable of withstanding strong impacts and high mechanical load.

### Key Components:
- Side gear plates
- Adjustable chain drivetrain
- Aluminum mounting plates
- Pinion gear subassembly
- Limelight camera and nameplate

### Challenges and Iteration:
- Coordinating with other robot subsystems introduced packaging and alignment constraints
- Structural aluminum plates underwent lightweighting process to reduce overall mass
- Manufacturing large gear arcs required careful multi-pass CNC machining
- Proper planning proved essential in balancing detailed design with time constraints

### Final Output:
The completed pivot subsystem proved to be a highly reliable and durable mechanism, consistently delivering accurate angle positioning and dependable performance throughout the competition season.

{% include image-gallery.html images="vaisala_hero.png" height="500" %}

---
## Component Breakdowns

### Side Gear Plates:
Large quarter-circle gear plates provide the main rotational interface for the structure. They were manufactured from 0.25” polycarbonate rather than aluminum to better absorb impacts and flex under load instead of cracking from internal stress. This material choice proved highly durable during competition, as the plates withstood repeated impacts without failure. Special attention was also given to the CNC manufacturing process to ensure the large gear teeth were cut cleanly across multiple machining passes.

{% include image-gallery.html images="vaisala_gears.png" height="300" %}
<span style="font-size: 10px"> </span>

### Adjustable Chain Drivetrain:
The pivot subsystem is powered by a chain drivetrain designed around an adjustable tensioning system to ensure reliable operation through wearing over time. An estimated sprocket spacing was implemented, while a smaller adjustable sprocket mounted to the side was incorporated to push against the chain and maintain proper tension. This approach simplified manufacturing tolerances while allowing the drivetrain to be tuned and serviced easily in competition.

{% include image-gallery.html images="vaisala_tension.png" height="300" %}
<span style="font-size: 10px"> </span>

### Aluminum Mounting Plates:
The pivot structure is supported by thick CNC-machined aluminum mounting plates that provide rigidity while connecting the drivetrain to the robot’s shooting deck assembly. The plates were lightweighted in CAD prior to manufacturing to reduce overall mass while still maintaining the necessary stiffness.

{% include image-gallery.html images="vaisala_plates.png" height="300" %}
<span style="font-size: 10px"> </span>

### Pinion Gear Subassembly:
Custom pinion gears engage with the side gear plates to rotate the pivot, controlling the angle of the shooting deck. Although the custom pinion gears themselves were designed by another team member, the surrounding drivetrain integration and the manufacturing of the pinion gears were central aspects of the development process.

{% include image-gallery.html images="vaisala_pinion.png" height="300" %}
<span style="font-size: 10px"> </span>

### Limelight Camera and Nameplate:
The front of the structure features both a Limelight vision camera and a custom robot nameplate. The camera provides targeting and odometry data used by the robot’s software to automatically shift launch angles during gameplay. The decorative nameplate displays the robot’s name in the team’s classic Space Age font, showcasing our team spirit and passion for aesthetic design.

{% include image-gallery.html images="vaisala_limelight.png" height="300" %}
<span style="font-size: 10px"> </span>
