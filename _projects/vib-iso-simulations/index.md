---
layout: post
title: Cryogenic Vibration Isolation System (Vib-Iso) Simulation Studies
description: Developed COMSOL Multiphysics models to evaluate the mechanical vibration response and cryogenic thermal performance of a ribbon-supported vibration isolation system for dilution refrigerator applications. Frequency-domain and thermal studies informed geometry selection and demonstrated the impact of thermal anchoring strategies on system performance.
skills: 
- COMSOL Multiphysics
- Mechanical Data Analyis
main-image: /sims_main3.png
---

---
## Mechanical Frequency Studies

### Objective:
This project used COMSOL Multiphysics to perform a frequency-domain mechanical analysis of the vibration isolation structure (Vib-Iso) to better understand its resonance behavior and support its future implementation in a dilution refrigerator. The study examined displacement, resonance frequencies, and deformation patterns under applied stress to evaluate how external forces influence structural stability.

### Model Setup:
The frequency study began with a simplified SolidWorks model of the structure, preserving the primary support features and ribbon geometry while omitting unnecessary details to improve simulation efficiency. Copper material properties were assigned using COMSOL’s built-in library, boundary conditions and loads were applied to represent operating constraints, and a refined mesh was used to balance accuracy and computation time.
{% include image-gallery.html images="sims_mech_model.png" height="400" %}
<span style="font-size: 10px">Original model vs. simplified redesign</span>

### Results
Simulations were performed for three effective ribbon lengths to examine how geometric variations affect resonance behavior, revealing that resonance frequencies shift systematically as ribbon length changes. The nominal ribbon length configuration (398.35 mm) showed lower displacement and acceleration than the shorter and longer variants (±10 mm). For each length, distinct peaks appear in the displacement response as a function of excitation frequency.

{% include image-gallery.html images="sims_mech_results1.png" height="300" %}
<span style="font-size: 10px">Frequency Modes Data</span>

Comparing across ribbon lengths, the extracted eigenfrequencies (first peaks) shift as the effective length is varied, demonstrating the sensitivity of the mechanical response to geometric parameters. In addition, the values extracted from the eigenmode analysis show that the 398 mm ribbon length exhibits the least displacement and acceleration of the three configurations.

{% include image-gallery.html images="sims_mech_results2.png" height="300" %}

---
## Thermal Dissipation Studies

### Objective:
Much like the refrigerator’s sensitivity to mechanical vibrations, inefficiencies in heat conduction through support structures can introduce unwanted thermal load. This study focused on characterizing the steady-state temperature distribution along the Vib-Iso and estimating the cooling behavior of the system over time. In particular, this analysis examined whether the inclusion of a copper braid improves heat conduction between different stages of the refrigerator.

### Model Setup:
The thermal simulations used the same simplified Vib-Iso geometry from the mechanical studies, with the addition of a copper braid to evaluate its effect on heat transfer. Idealized cryogenic boundary conditions were applied to represent thermal connections to the dilution refrigerator stages, while all other surfaces were treated as insulated so heat transfer occurred only through conduction. Simulations were performed both with and without the copper braid, using stationary and time-dependent analyses to compare steady-state thermal behavior and cooldown performance. Radiative and convective heat transfer, as well as contact resistance effects, were excluded to reflect high-vacuum cryogenic operating conditions.

### Results:
The stationary thermal simulation including the copper braid shows a smooth temperature gradient along the ribbon length, with heat conducted from the 100 mK boundary toward the 4 mK thermal anchor. The lower regions of the structure approach the colder temperature, indicating that the copper braid provides an efficient conductive pathway. The time-dependent (24-hour) thermal simulation illustrates how the structure cools over time, with the cooling front propagating from the colder boundary upward through the ribbon supports.

{% include image-gallery.html images="sims_therm_results5.png" height="300" %}
<span style="font-size: 10px">Without Braid (Time-Dependent, Stationary) & With Braid (Time-Dependent, Stationary)</span>

These studies also proved that the inclusion of a copper braid allowed the system to cool significantly faster and to lower final temperatures. Without the braid, heat dissipation relies solely on conduction through the ribbon supports, resulting in less effective cooling.

{% include image-gallery.html images="sims_therm_results3.png" height="300" %}

## Embedding images 
### External images
{% include image-gallery.html images="https://live.staticflickr.com/65535/52821641477_d397e56bc4_k.jpg, https://live.staticflickr.com/65535/52822650673_f074b20d90_k.jpg" height="400"%}
<span style="font-size: 10px">"Starship Test Flight Mission" from https://www.flickr.com/photos/spacex/52821641477/</span>  
You can put in multiple entries. All images will be at a fixed height in the same row. With smaller window, they will switch to columns.  

### Embeed images
{% include image-gallery.html images="project2.jpg" height="400" %} 
place the images in project folder/images then update the file path.   


## Embedding youtube video
The second video has the autoplay on. copy and paste the 11-digit id found in the url link. <br>
*Example* : https://www.youtube.com/watch?v={**MhVw-MHGv4s**}&ab_channel=engineerguy
{% include youtube-video.html id="MhVw-MHGv4s" autoplay= "false"%}
{% include youtube-video.html id="XGC31lmdS6s" autoplay = "true" %}

you can also set up custom size by specifying the width (the aspect ratio has been set to 16/9). The default size is 560 pixels x 315 pixels.  

The width of the video below. Regardless of initial width, all the videos is responsive and will fit within the smaller screen.
{% include youtube-video.html id="tGCdLEQzde0" autoplay = "false" width= "900px" %}  

<br>

## Adding a hozontal line
---

## Starting a new line
leave two spaces "  " at the end or enter <br>

## Adding bold text
this is how you input **bold text**

## Adding italic text
Italicized text is the *cat's meow*.

## Adding ordered list
1. First item
2. Second item
3. Third item
4. Fourth item

## Adding unordered list
- First item
- Second item
- Third item
- Fourth item

## Adding code block
```ruby
def hello_world
  puts "Hello, World!"
end
```

```python
def start()
  print("time to start!")
```

```javascript
let x = 1;
if (x === 1) {
  let x = 2;
  console.log(x);
}
console.log(x);

```

## Adding external links
[Wikipedia](https://en.wikipedia.org)


## Adding block quote
> A blockquote would look great if you need to highlight something


## Adding table 

| Header 1 | Header 2 |
|----------|----------|
| Row 1, Col 1 | Row 1, Col 2 |
| Row 2, Col 1 | Row 2, Col 2 |

make sure to leave aline betwen the table and the header
