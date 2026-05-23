---
layout: post
title: Engineering Design & Drawings of Vibration Isolation System
description: Translated simulation data and conclusions into fabrication-ready hardware through detailed CAD modeling and engineering drawing development. Produced manufacturing documentation for cryogenic-compatible components while incorporating manufacturability and integration requirements.
skills: 
- SolidWorks
- Technical Drawings
main-image: /project.webp 
---

---
## Redesign Process
Simplifications made during simulation were revisited and adjusted where necessary to ensure the designs better reflected their respective function while preserving the key features that influence mechanical and thermal performance. These changes include:
- Adding pattern holes to the base plate for secure integration
- Reintroducing full paired clamp design (body + cap)
- Updating curved ribbon geometry to preserve line of sight for mounted optical components.

{% include image-gallery.html images="sims_mech_model.png" height="300" %}
<span style="font-size: 10px">Simplified COMSOL model vs. new detailed model</span>

Initial drawings were reviewed and revised to address issues related to fit, alignment, and manufacturability, with feedback from lab members guiding successive refinements.

---
## Drawings and Specifications

Much like the refrigerator’s sensitivity to mechanical vibrations, inefficiencies in heat conduction through support structures can introduce unwanted thermal load. This study focused on characterizing the steady-state temperature distribution along the Vib-Iso and estimating the cooling behavior of the system over time. In particular, this analysis examined whether the inclusion of a copper braid improves heat conduction between different stages of the refrigerator.

### Model Setup:
The thermal simulations used the same simplified Vib-Iso geometry from the mechanical studies, with the addition of a copper braid to evaluate its effect on heat transfer. Idealized cryogenic boundary conditions were applied to represent thermal connections to the dilution refrigerator stages, while all other surfaces were treated as insulated so heat transfer occurred only through conduction. Simulations were performed both with and without the copper braid, using stationary and time-dependent analyses to compare steady-state thermal behavior and cooldown performance. Radiative and convective heat transfer, as well as contact resistance effects, were excluded to reflect high-vacuum cryogenic operating conditions.

### Results:
The stationary thermal simulation including the copper braid shows a smooth temperature gradient along the ribbon length, with heat conducted from the 100 mK boundary toward the 4 mK thermal anchor. The lower regions of the structure approach the colder temperature, indicating that the copper braid provides an efficient conductive pathway. The time-dependent (24-hour) thermal simulation illustrates how the structure cools over time, with the cooling front propagating from the colder boundary upward through the ribbon supports.

{% include image-gallery.html images="sims_therm_results5.png" height="300" %}
<span style="font-size: 10px">From left to right: Time-dependent (without braid), Stationary (without braid), Time-dependent (with braid), Stationary (with braid)</span>

These studies also proved that the inclusion of a copper braid allowed the system to cool significantly faster and to lower final temperatures. Without the braid, heat dissipation relies solely on conduction through the ribbon supports, resulting in less effective cooling.

{% include image-gallery.html images="sims_therm_results3.png" height="300" %}
