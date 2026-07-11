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

{% include image-gallery.html images="asag.png" height="300" %}
<span style="font-size: 10px"></span>

Because changing substrate dimensions alters both resonance frequencies and mode behavior, manually evaluating hundreds of possible geometries would be impractical.

### Theory Constraints
For a resonator to produce stable Gaussian displacement fields, we depend on a stability range of... 0 < g < 1

The beam waist (w0​) and beam radius at the dome surface (w2) can be calculated analytically. To minimize leakage, the beam must remain well confined beneath the dome. This work uses the semi-arbitrary criterion... a / w2 ≥ 3

{% include image-gallery.html images="workflow2.png" height="300" %}
<span style="font-size: 10px">Parameter influence path</span>

To visualize how the geometry parameters relate to each other and what acceptable substrate composition might look like, 4 colormap graphs were produced in MATLAB based on an aperture range of 1 to 300 μm and a sag range of 0.05 to 1 μm, each showcasing a different optimization feature.

### Map 1 – Resonator Stability
Goal: Determine which substrate geometries can theoretically support stable Gaussian HBAR modes at 4 GHz.

Key Points:
- Stable Gaussian modes require 0 < g < 1
- White region corresponds to unstable geometries, colored region represents valid values of g
- Red contour marks the stability boundary (g = 0)

{% include image-gallery.html images="stability.png" height="300" %}
<span style="font-size: 10px"></span>

Takeaway: Only geometries within the stable region are considered for further HBAR design analysis.

### Map 2 – Valid Geometry Region

Goal: Identify substrate geometries that satisfy both stability and beam confinement requirements at 4 GHz.

Key Points:
- Only valid if 0 < g < 1 and a / w2 ≥ 3
- Green regions satisfy both criteria simultaneously, white regions fail one or more design requirements.

{% include image-gallery.html images="valid.png" height="300" %}
<span style="font-size: 10px"></span>

Takeaway: Provides a quick pass/fail assessment of candidate substrate geometries before running simulations.

### Map 3 – Containment Factor Gradient

Goal: Visualize how resonator stability and beam confinement jointly limit the feasible design space at 4 GHz.

Key Points:
- Colormap represents the beam containment factor (a / w2) at any given (a, sag) combination.
- Black contour marks the containment requirement (a / w2 = 3).

{% include image-gallery.html images="containment.png" height="300" %}
<span style="font-size: 10px"></span>

Takeaway: Explains why certain geometries are feasible while others fail, making it a useful design-space exploration tool.

### Map 4 – Minimum Frequency for Beam Containment

Goal: Determine the minimum operating frequency required for each substrate geometry to achieve beam confinement.

Key Points:
- Colormap shows the minimum frequency required to satisfy the containment criterion (a / w2 ≥ 3).
- White region corresponds to frequencies outside the practical design range (> 20 GHz).

{% include image-gallery.html images="minfreq.png" height="300" %}
<span style="font-size: 10px"></span>

Takeaway: Enables geometry design selection based on target operating frequency.

### COMSOL Validation

Objective: Use four representative substrate geometries for COMSOL simulations and verify that well-confined HBAR modes are found.

Tested (a, sag) combinations:
- (200, 1)
- (300, 0.2)
- (150, 0.5)
- (110, 1)

{% include image-gallery.html images="valid2.png" height="300" %}
<span style="font-size: 10px"></span>

All four geometric configurations produced effecitve, well-confined HBAR modes. Their displacement profiles were fitted to Hermite-Gaussian theory (same logic as above) and resulted in consistently high R² scores.

{% include image-gallery.html images="config_modes.png" height="300" %}
<span style="font-size: 10px">Example HBAR modes found for each geometric configuration</span>
