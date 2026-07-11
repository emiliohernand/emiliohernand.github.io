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
## Hermite-Gaussian Mode Characterization

### Objective
Develop an automated framework for identifying High Overtone Bulk Acoustic Resonator (HBAR) modes from simulated mechanical eigenmodes. The goal was to replace manual inspection of COMSOL results with a repeatable classification process based on theoretical mode shapes and statistical curve fitting.

### Background
HBAR devices support a large number of closely spaced mechanical resonances, many of which are not useful operating modes. Although COMSOL can accurately calculate these eigenmodes, determining which modes exhibit true HBAR behavior traditionally requires manual inspection of displacement profiles.

{% include image-gallery.html images="base_model.png" height="300" %}
<span style="font-size: 10px">Base COMSOL model (exagerated dome geometry)</span>

To eliminate this bottleneck, I developed a MATLAB-based characterization workflow capable of automatically identifying HBAR modes directly from COMSOL simulation data.

{% include image-gallery.html images="example_hbar.png" height="300" %}
<span style="font-size: 10px">Example HBAR mode vs. non-HBAR mode</span>

### Predicting Candidate Resonances
The workflow begins by calculating the theoretical resonance frequencies associated with a specified range of longitudinal overtone numbers. These predicted frequencies serve as reference points for automated COMSOL eigenfrequency searches.

Rather than searching across the entire frequency spectrum, the simulation performs localized searches around each theoretical resonance, significantly reducing computational cost while ensuring that nearby HBAR modes are captured.

{% include image-gallery.html images="theory_console.png" height="300" %}
<span style="font-size: 10px">Example theoretical frequency locations</span>

### Extracting Mode Profiles
Each eigenfrequency search returns multiple mechanical eigenmodes. For every mode identified, the radial displacement profile is extracted along a cut line through the substrate.

This one-dimensional displacement profile captures the transverse shape of the mechanical mode and serves as the input for the characterization algorithm implemented in MATLAB.

{% include image-gallery.html images="cutline_location.png" height="300" %}
<span style="font-size: 10px">Cutline location in subtrate</span>

### Hermite-Gaussian Curve Fitting
The exported displacement profile is compared against a library of theoretical transverse mode distributions, dictated by mathematical Hermite-Gaussian models.

{% include image-gallery.html images="example_curves.png" height="300" %}
<span style="font-size: 10px">Example Hermite-Gaussian displacement curves</span>

A custom nonlinear least-squares fitting routine determines the optimal amplitude, beam width, and center position for every candidate distribution. The coefficient of determination (R²) is then calculated for each fit, allowing the algorithm to identify which theoretical mode most closely matches the simulated displacement profile.

{% include image-gallery.html images="example_fits.png" height="300" %}
<span style="font-size: 10px">Example MATLAB profile fits</span>

This approach provides an objective method for distinguishing HBAR modes from spurious mechanical resonances while simultaneously verifying that the transverse mode order is found roughly in the expected location.

### Automated HBAR Classification
After evaluating every candidate distribution, the workflow selects the model with the highest goodness-of-fit. Modes whose best-fit R² exceeds a predefined threshold are automatically classified as HBAR candidates.

{% include image-gallery.html images="workflow.png" height="300" %}
<span style="font-size: 10px">Full MATLAB workflow</span>

Relevant information—including resonance frequency, overtone number, best-fit distribution, fitting parameters, and R² value—is compiled into a single output table for further analysis.

{% include image-gallery.html images="full_candidate_table.png" height="300" %}
<span style="font-size: 10px">Final HBAR candidate table</span>

The entire characterization process was integrated into a hierarchical MATLAB framework that interfaces directly with COMSOL through LiveLink, enabling automated simulation, data extraction, mode identification, and reporting.

---
## Device Geometry Optimization

### Objective
Develop simulation tools to investigate how substrate geometry influences HBAR resonance behavior and identify device dimensions that improve mode confinement while maintaining practical operating frequencies.

### Background
After establishing an automated method for identifying HBAR modes, the next step was to determine how device geometry affects their performance. Two geometric design parameters define the dome:
- Aperture (a) – the half-width of the domed region
- Sag (sag) – the height of the dome above the substrate

{% include image-gallery.html images="asag_table.png" height="300" %}
<span style="font-size: 10px"></span>

Because changing substrate dimensions alters both resonance frequencies and mode behavior, manually evaluating hundreds of possible geometries would be impractical. To address this challenge, I developed a MATLAB framework capable of analyzing large parametric simulation datasets and visualizing the resulting design space.

### Parametric COMSOL Studies
A series of COMSOL simulations was performed while varying key substrate dimensions across predefined ranges. For each geometry, resonance frequencies were calculated and exported for post-processing.

These simulations generated a large dataset relating geometric parameters to predicted HBAR operating frequencies.

Suggested images
- COMSOL parametric sweep settings
- Geometry variations

### MATLAB Data Processing
Custom MATLAB scripts organized the simulation results into structured datasets suitable for visualization and analysis.

Mathematical relationships between the geometric parameters and resonance frequencies were then used to identify trends throughout the design space. Automated filtering techniques were also implemented to remove unrealistic frequency regions, improving the readability of the resulting plots.

Suggested images
- MATLAB code snippet
- Data organization diagram

### Design Space Visualization
Processed simulation results were visualized using contour plots that map resonance frequency as a function of substrate geometry.

These plots provide an intuitive method for identifying combinations of dimensions capable of supporting desired operating frequencies while simultaneously revealing regions where HBAR behavior becomes impractical.

The resulting visualization tools enable rapid design exploration without requiring repeated manual inspection of individual simulations.

Suggested images
- Your frequency contour plots
- Highlighted optimal region
- Before/after filtering comparison
