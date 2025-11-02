---
title: "Pi in the sky: Launch 1"
description: "The maiden launch of the high-altitude balloon program carrying scientific experiments to the stratosphere."
author: yves
date: 2025-04-30 12:00:00 +0200
categories: [Pi in the Sky]
tags: [stratospheric, balloon, science, physics, engineering, data processing, spectrometer, spectra, pi in the sky]
pin: false
math: true
recent-project: false
mermaid: false
media_subpath: /assets/posts/pi_in_the_sky/

image:
  path: /stratospheric_launch_1/pictures/walking_the_balloon.jpg
  lqip: data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDABALDA4MChAODQ4SERATGCgaGBYWGDEjJR0oOjM9PDkzODdASFxOQERXRTc4UG1RV19iZ2hnPk1xeXBkeFxlZ2P/2wBDARESEhgVGC8aGi9jQjhCY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2P/wAARCAALABQDASIAAhEBAxEB/8QAHwAAAQUBAQEBAQEAAAAAAAAAAAECAwQFBgcICQoL/8QAtRAAAgEDAwIEAwUFBAQAAAF9AQIDAAQRBRIhMUEGE1FhByJxFDKBkaEII0KxwRVS0fAkM2JyggkKFhcYGRolJicoKSo0NTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uHi4+Tl5ufo6erx8vP09fb3+Pn6/8QAHwEAAwEBAQEBAQEBAQAAAAAAAAECAwQFBgcICQoL/8QAtREAAgECBAQDBAcFBAQAAQJ3AAECAxEEBSExBhJBUQdhcRMiMoEIFEKRobHBCSMzUvAVYnLRChYkNOEl8RcYGRomJygpKjU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6goOEhYaHiImKkpOUlZaXmJmaoqOkpaanqKmqsrO0tba3uLm6wsPExcbHyMnK0tPU1dbX2Nna4uPk5ebn6Onq8vP09fb3+Pn6/9oADAMBAAIRAxEAPwCrEitjGD9DSyWwIzg5rjldx0Yj8akFxMOkzj/gRrfmQtToXtzu6UVz32qf/ns//fVFK6Hc/9k=
  alt: Walking the Helium-filled latex balloon to the launch site with the parachute and payload box attached. Taken by Marieke Vereycken.
---
LQIP
Pi in the Sky is a student-led high-altitude balloon program combining engineering and physics to carry scientific payloads into the stratosphere. See the [main project post](../Pi-in-the-sky/) for a general overview. 


On 27/04/2025, the first ever Pi in the Sky launch took place, lifting off from Thor Park ($50.994938^\circ\,\mathrm{N}$, $5.538705^\circ\,\mathrm{E}$). As the project’s inaugural flight, the launch tested key systems including GPS tracking, APRS telemetry, and onboard imaging.


Weather conditions were excellent, with a clear blue sky and calm winds. The balloon was released at around 11:00 LT and rose steadily into the stratosphere. After a smooth ascent into the sky and bursting at an altitude of $41.60 \,\mathrm{km}$, it descended and landed safely in the Maas River in Maastricht, Netherlands. The payload was promptly recovered from the water with the help of the local water club. The mission was a complete success, with a flawless launch, safe recovery, and experiment data collected.

## Launch

With the help of volunteers and the team, the balloon was carefully prepared and safely released under great applause. Watch the video below to experience the launch firsthand.
{% include embed/youtube.html id='4T7pkLAxnXs' %}

## Results

With the gondola and experiments successfully recovered, we are pleased to present our findings. The measurements provide a detailed profile of atmospheric conditions and UV spectra from the surface up to an altitude of approximately $42\,\mathrm{km}$.

### Atmospheric pressure

The atmospheric pressure was measured at intervals of $30\,\mathrm{s}$ and synchronized with the local time of the launch. At the peak of the flight, a pressure of $8.62 \, \mathrm{hPa}$ was recorded. This is considered a low vacuum, although it remains several orders of magnitude higher than pressures typically achieved in laboratory vacuum chambers.

![light mode](stratospheric_launch_1/pressure_graph_white.png){: .light }
![dark mode](stratospheric_launch_1/pressure_graph_black.png){: .dark } 

### Altitude vs Time
As both atmospheric pressure and outside temperature were measured during flight, it is possible to calculate the altitude using the barometric formula,[^barometric_formula]

$$
P = P_0 \,\exp\left(\frac{-m\,g\,h}{k\,T}\right)
$$

or in molar form, with substitutions of molar mass and Boltzmann constant relation, $m = \frac{M}{N_A}$ and $k = \frac{R}{N_A}$,

$$
\begin{align*}
P &= P_0\,\exp\left(\frac{-\frac{M}{N_A}\,g\,h}{ \frac{R}{N_A}\,T}\right) \\
  &= P_0\,\exp\left(\frac{-Mg\,h}{RT}\right)
\end{align*}
$$

Now define altitude as the height above the terrain level, $h = h' - h_0$,

$$
P = P_0 \, \exp\left(\dfrac{-g\,M(h'-h_0)}{RT}\right)
$$


rearranging the equation gives a form for calculating current altitude $h'$,

$$
h' = h_0 + \frac{R \, T}{g \, M} \, \ln\!\left(\frac{P_0}{P}\right)
$$

with $P$ and $T$ as the atmospheric pressure and temperature at altitude, $P_0 = 1014.58 \,\text{hPa}\,$ as the sea-level pressure on 27/04/2025, $h_0 = 80 \,\text{m}$ as the sea-level altitude of the launch site, $g = 9.80665 \,\text{m/s}^2$ as the gravitational acceleration, $M = 0.0289644 \,\text{kg/mol}$ as the molar mass of air, and $R = 8.31432 \,\text{J/(mol·K)}$ as the universal gas constant.

Using this formula, the measured pressure and temperature data can be converted into altitude values throughout the flight. 

![light mode](stratospheric_launch_1/altitude_graph_white.png){: .light }
![dark mode](stratospheric_launch_1/altitude_graph_black.png){: .dark } 

### Temperature vs Altitude
Plotting the outside temperature measurements as a function of altitude during the ascent phase shows a nearly inverse linear relation between temperature and altitude up to around $11 \,\mathrm{km}$, after which the temperature begins to increase again. This corresponds to the transition from the troposphere to the stratosphere.[^noaa_atmosphere] 
During this mission, the temperature dropped to a minimum of $-36.75\,^\circ\mathrm{C}$ before rising to $23.38\,^\circ\mathrm{C}$ at the peak of the flight at $41.60 \,\mathrm{km}$.

![light mode](stratospheric_launch_1/temperature_graph_white.png){: .light }
![dark mode](stratospheric_launch_1/temperature_graph_black.png){: .dark } 


### Ascent rate vs Time
By computing the numerical derivative of the Altitude vs Time data, we obtain the Ascent rate vs Time graph. This clearly show three distinct phases of the mission: the ground phase, the ascent phase, and the descent phase.

![light mode](stratospheric_launch_1/ascent_rate_graph_white.png){: .light }
![dark mode](stratospheric_launch_1/ascent_rate_graph_black.png){: .dark } 

The average ascent rate during the ascent phase is $\approx 3.506\,\mathrm{m/s}$, tending upwards before reaching the peak and after the balloon bursts, accelerating quickly to terminal velocity of $\approx -85.37\,\mathrm{m/s}$.

## Recovery

## Conclusion

<figure class="right" style="width:30%;">
  <img src="stratospheric_launch_1/pictures/group_photo_after.jpg" 
       alt="Group photo taken immediately after launch, with the balloon faintly visible in the background" 
       style="width:100%; height:auto;">
  <figcaption class="text-center text-muted post-meta">
    Group photo taken immediately after launch, with the balloon faintly visible in the background.
  </figcaption>
</figure>

Immediately after launch, it was observed that the APRS telemetry packets did not contain valid GPS coordinates. Subsequent analysis and testing indicated that, in the current configuration, the GPS antenna was obstructed by the thermal blanket wrapped around the gondola, preventing GPS satellite reception.

The Raspberry Pi camera also unfortunately failed to record any images, despite being connected to the power bank. We discovered that to enable dual-port output, the power button must be pressed a second time; otherwise, no power is supplied. This is something to improve upon for the next launch.

But despite the tracking and camera issues, the first launch was a great success. We managed to capture UV spectra as well as temperature and pressure data throughout the entire flight and were able to recover the payload box and parachute.


Many thanks to my teammates **Wout Stulens** and **Achiel Seynhaeve**, our partners and volunteers for helping us make this launch mission possible.
If you’re interested in the raw data or wish to send an experiment to the stratosphere (preferably high school students), feel free to contact me.


| ![light mode](logo's/phoenix.png){: .light width="970"} ![dark mode](logo's/phoenix.png){: .dark width="970"} | ![light mode](logo's/physxlab_white.png){: .light } ![dark mode](logo's/physxlab_black.png){: .dark } | ![light mode](logo's/uhasselt_white.png){: .light } ![dark mode](logo's/uhasselt_black.png){: .dark } | ![light mode](logo's/VTI_ieper_white.png){: .light width="970"} ![dark mode](logo's/VTI_ieper_black.png){: .dark width="970" } | ![light mode](logo's/shd_white.png){: .light } ![dark mode](logo's/shd_white.png){: .dark } |
{: .trans-table}

<figcaption class="text-center text-muted post-meta">
   This work does not represent the views of any our partners.
</figcaption>

## Sources

[^barometric_formula]: LibreTexts Chemistry. (2023). 2.11: The Barometric Formula. Retrieved from [https://chem.libretexts.org/Bookshelves/Physical_and_Theoretical_Chemistry_Textbook_Maps/Thermodynamics_and_Chemical_Equilibrium_(Ellgen)/02%3A_Gas_Laws/2.11%3A_The_Barometric_Formula](https://chem.libretexts.org/Bookshelves/Physical_and_Theoretical_Chemistry_Textbook_Maps/Thermodynamics_and_Chemical_Equilibrium_(Ellgen)/02%3A_Gas_Laws/2.11%3A_The_Barometric_Formula)
[^noaa_atmosphere]: *Layers of the Atmosphere - National Oceanic and Atmospheric Administration.* Accessed March 12, 2025. [https://www.noaa.gov/jetstream/atmosphere/layers-of-atmosphere](https://www.noaa.gov/jetstream/atmosphere/layers-of-atmosphere)
