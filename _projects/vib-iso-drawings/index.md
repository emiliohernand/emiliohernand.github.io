---
layout: post
title: Engineering Design & Drawings of Vibration Isolation System
description: Translated simulation data and conclusions into fabrication-ready hardware through detailed CAD modeling and engineering drawing development. Produced manufacturing documentation for cryogenic-compatible components while incorporating manufacturability and integration requirements.
skills: 
- SolidWorks
- Technical Drawings
main-image: /drawings_main1.png
---

---
## Redesign Process
Simplifications made during simulation were revisited and adjusted where necessary to ensure the designs better reflected their respective function while preserving the key features that influence mechanical and thermal performance. These changes include:
- Adding pattern holes to the base plate for secure integration
- Reintroducing full paired clamp design (body + cap)
- Updating curved ribbon geometry to preserve line of sight for mounted optical components.

{% include image-gallery.html images="drawings1.png" height="300" %}
<span style="font-size: 10px">Simplified COMSOL model vs. new detailed model</span>

Initial drawings were reviewed and revised to address issues related to fit, alignment, and manufacturability, with feedback from lab members guiding successive refinements.

---
## Drawings and Specifications
All components of the Vib-Iso were designed for oxygen-free high-conductivity (OFHC) copper manufacturing, selected for its excellent thermal conductivity and mechanical integrity, eliminating the need for additional surface treatment or coatings. The engineering drawings define fully dimensioned geometries in millimeters and include standard manufacturing notes, such as depth of drilling and isometric angles for clarity.

{% include image-gallery.html images="drawings2.png" height="1600" %}

Across all parts, the specifications prioritize clear definition of geometry and interfaces to ensure manufacturability and compatibility within the larger Vib-Iso assembly, while remaining consistent with the mechanical and thermal requirements.

---
## Challenges and Solutions
While the underlying geometry of the Vib-Iso components was straightforward in a CAD environment, translating that geometry into drawings required careful attention to detail. One recurring difficulty was representing internal features that are not visible from external views, such as drilled and tapped holes. This required the use of section views and hidden lines to ensure that critical features were fully defined without ambiguity.

As more features were added, it became increasingly important to organize labels, avoid clutter, and preserve readability. This was addressed through iterative refinement of drawing layouts, including repositioning dimensions, using multiple views where necessary, and prioritizing the most critical information.

Following the development of the full drawing set and the successful procurement of a third-party manufacturer, all components have since been completed and delivered.
