---
title: "Pi in the sky: stratospheric balloon program"
description: "A student-led high-altitude balloon program using a custom-built UV spectrometer to measure atmospheric trace gases and demonstrate low-cost space science."
author: yves
date: 2025-08-29 12:00:00 +0200
categories: [Pi in the Sky]
tags: [stratospheric, balloon, science, physics, engineering, spectrometer, spectra, pi in the sky, experiment]
pin: false
recent-project: true
math: false
mermaid: true
media_subpath: /assets/posts/pi_in_the_sky

image:
  path: beautiful_planet.jpg
  lqip: data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDABALDA4MChAODQ4SERATGCgaGBYWGDEjJR0oOjM9PDkzODdASFxOQERXRTc4UG1RV19iZ2hnPk1xeXBkeFxlZ2P/2wBDARESEhgVGC8aGi9jQjhCY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2P/wAARCAALABQDASIAAhEBAxEB/8QAHwAAAQUBAQEBAQEAAAAAAAAAAAECAwQFBgcICQoL/8QAtRAAAgEDAwIEAwUFBAQAAAF9AQIDAAQRBRIhMUEGE1FhByJxFDKBkaEII0KxwRVS0fAkM2JyggkKFhcYGRolJicoKSo0NTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uHi4+Tl5ufo6erx8vP09fb3+Pn6/8QAHwEAAwEBAQEBAQEBAQAAAAAAAAECAwQFBgcICQoL/8QAtREAAgECBAQDBAcFBAQAAQJ3AAECAxEEBSExBhJBUQdhcRMiMoEIFEKRobHBCSMzUvAVYnLRChYkNOEl8RcYGRomJygpKjU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6goOEhYaHiImKkpOUlZaXmJmaoqOkpaanqKmqsrO0tba3uLm6wsPExcbHyMnK0tPU1dbX2Nna4uPk5ebn6Onq8vP09fb3+Pn6/9oADAMBAAIRAxEAPwCrEitjGD9DSyWwIzg5rjldx0Yj8akFxMOkzj/gRrfmQtToXtzu6UVz32qf/ns//fVFK6Hc/9k=
  alt: The Earth from 37 km altitude, showing Belgium and the Netherlands’ coastline with a few clouds overhead.
---

Pi in the Sky is a student-led high-altitude balloon program combining engineering and physics to carry scientific payloads into the stratosphere. The project demonstrates how lightweight, low-cost designs can be used to conduct meaningful atmospheric research, while also providing hands-on experience in construction, data collection, and navigation under real-world conditions.

The UV spectrometer, developed within the project, was designed using 3D-printed components and equipped with optical elements to analyze sunlight absorption in the UV range. Launched twice into the stratosphere (up to ~41 km), it collected over 130 GB of data, demonstrating the feasibility of low-cost atmospheric spectroscopy and providing insights into solar spectra and trace gas detection.

### Payloads
There were 2 scientific payloads onboard of the gondola, our self developed [UV spectrometer](#) to measure trace gas concentrations in the atmosphere and a highschool experiment by the **Vrij Technisch Instituut** in **Ieper** measuring exterior and interior temperatures and atmospheric pressure. Allowing for the creation of altitude, ascent rate and temperature graphs.

As we wanted to capture the curvature and atmosphere of our beautiful planet, we equipped the gondola with an [Raspberry Pi Zero powered camera](#) capturing the vista's on the outside of the balloon. 

In order to track the balloon, we equipped the gondola with an [self-designed APRS tracker](#) and a backup TKstar GPS tracker. The APRS tracker sends live telemetry packets with location, altitude and time on the amateur APRS radio frequency of 144.8 MHz at a rate of one packet every minute. The backup TKstar tracker has an internal sim card which upon sending a specific command will return the last known GPS location and cell tower. These two systems provide a decent chance of recovery of the gondola and integrated scientific payloads but still rely on the reception of GPS signals.


### Construction
<figure class="right" style="width:35%;">
  <img src="balloon_construction.jpg" 
       alt="Assembly snapshot of stratospheric balloon experiment." 
       style="width:100%; height:auto;">
  <figcaption class="text-center text-muted post-meta">
    Assembly snapshot of stratospheric balloon experiment.
  </figcaption>
</figure>

A properly constructed stratospheric balloon is a carefully designed system that combines multiple components to safely carry scientific instruments to the upper atmosphere. It includes:

- **Balloon**: elastic vessel for the lifting gas, filled with Helium to provide an ascent rate of larger than 5m/s.

- **Parachute**: a parachute to slow descent velocity to below 7 m/s in order to prevent damage to people and property

- **Gondola**: payload box with scientific experiments and tracking equipment. Ideally a stryofoam box to shield the inside electronics from large temperature gradients.

- **Cordline**: to connect all the parts together, a special safety cord is used that breaks under a loading of 180N.

### Legal and regulatory 

The legal procedures for launching a stratospheric balloon vary widely by location, this is only a rough outline for Belgium.
In short, to launch a stratospheric balloon legally, you need to prepare the following documents:
- Full technical description of materials, experiments and construction of the gondola
- Launch site permission
- Approval of city council
- Insurance for balloon launch and ground activities (clearly stating touchdown coverage in neighboring countries!)

Then you can fill in the stratospheric balloon launch form of relevant *Air Traffic Services* (ATS), in our case *Directoriaat-Generaal Luchtvaart* (DGLV) and apply for approval. The application must be submitted **no later than 20 and no earlier than 60 working days** before the planned launch date. Upon being granted approval, the ATS may mandate certain actions. As we had selected a launch site in the vicinity of Zwartberg Airfield (EBZW), we had to inform the aerodrome management of our activities.

We chose to apply to launch on two launch dates, the primary date of 27/04/2025 and in the event of bad weather (excess wind, thunderstorms, etc.) a backup date of 11/05/2025. 

(Disclaimer: This is not legal advice!)

### Results

In total, we had two succesful balloon launches with excellent weather on both occasions. While originally planning for one launch, the stars aligned for a second launch: we made a full recovery of the gondola on the first launch, excellent weather predictions, approval for a second launch and had enough material for a second launch.  For detailed information and experiment data see:
- [Pi in the sky: Launch 1](#)
- [Pi in the sky: Launch 2](#)

### Local news

We invited local press and radio amateur clubs, along with friends and family, to witness the launches.
- [Nieuwblad](https://www.nieuwsblad.be/cnt/dmf20250514_95358416)
- [Het belang van Limburg](https://www.hbvl.be/regio/limburg/genk/wetenschap-op-35-kilometer-hoogte-studenten-laten-ballon-op-voor-metingen-in-stratosfeer/62352148.html)
- [ON4MLB](https://www.on4mlb.be/2025/05/limburgse-studenten-meten-ozon-met-stratosfeerballon/)
- [HamCon](https://www.linkedin.com/posts/hamcon-belgium_limburgse-studenten-meten-ozon-met-stratosfeerballon-activity-7328676461203120129-_op5/)


### Special thanks  
This project would not have been possible without the generous support and collaboration of our partners and teammates:  
- **Team members Achiel Seynhaeve and Wout Stulens** – for their creativity, dedication, and teamwork throughout the entire journey.  
- **UHasselt and PhysX Lab** – for sponsoring material costs of the balloon and gondola, providing optical components for the UV spectrometer, and granting access to technical facilities.  
- **VTI Ieper (secundary school)** – for partially funding the project, ensuring future launch capability, and trusting us with their experiment.  
- **Dirk Geeroms** – for help in coordinating the project, managing Helium logistics and securing launch site access.


| ![light mode](logo's/phoenix.png){: .light width="970"} ![dark mode](logo's/phoenix.png){: .dark width="970"} | ![light mode](logo's/physxlab_white.png){: .light } ![dark mode](logo's/physxlab_black.png){: .dark } | ![light mode](logo's/uhasselt_white.png){: .light } ![dark mode](logo's/uhasselt_black.png){: .dark } | ![light mode](logo's/VTI_ieper_white.png){: .light width="970"} ![dark mode](logo's/VTI_ieper_black.png){: .dark width="970" } | ![light mode](logo's/shd_white.png){: .light } ![dark mode](logo's/shd_white.png){: .dark } |
{: .trans-table}

<figcaption class="text-center text-muted post-meta">
   This work does not represent the views of any our partners.
</figcaption>