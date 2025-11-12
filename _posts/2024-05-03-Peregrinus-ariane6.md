---
title: "Peregrinus experiment on Ariane 6 maiden voyage"
description: "A collaborative trilingual student experiment developed in Belgium and launched on the maiden flight of the Ariane 6 rocket."
author: yves
date: 2024-07-13 12:00:00 +0200
categories: [Space]
tags: [space, esa, ariane 6, science, physics, engineering, experiment]
pin: false
math: false
recent-project: true
mermaid: false
media_subpath: /assets/posts/peregrinus

image:
  path: peregrinus_experiment.jpg
  lqip: data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDABALDA4MChAODQ4SERATGCgaGBYWGDEjJR0oOjM9PDkzODdASFxOQERXRTc4UG1RV19iZ2hnPk1xeXBkeFxlZ2P/2wBDARESEhgVGC8aGi9jQjhCY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2NjY2P/wAARCAANABQDASIAAhEBAxEB/8QAHwAAAQUBAQEBAQEAAAAAAAAAAAECAwQFBgcICQoL/8QAtRAAAgEDAwIEAwUFBAQAAAF9AQIDAAQRBRIhMUEGE1FhByJxFDKBkaEII0KxwRVS0fAkM2JyggkKFhcYGRolJicoKSo0NTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uHi4+Tl5ufo6erx8vP09fb3+Pn6/8QAHwEAAwEBAQEBAQEBAQAAAAAAAAECAwQFBgcICQoL/8QAtREAAgECBAQDBAcFBAQAAQJ3AAECAxEEBSExBhJBUQdhcRMiMoEIFEKRobHBCSMzUvAVYnLRChYkNOEl8RcYGRomJygpKjU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6goOEhYaHiImKkpOUlZaXmJmaoqOkpaanqKmqsrO0tba3uLm6wsPExcbHyMnK0tPU1dbX2Nna4uPk5ebn6Onq8vP09fb3+Pn6/9oADAMBAAIRAxEAPwAbV71LhBCkTRMMxys5UEY5xU8Wu3RB85woKlvlJPA69aathb3PzyRLlScY4x+VTy6daAkrbxjIweM5FFwsVm1K1mIkME0rMAS4HBNFSmILgJtUY6BaKm7HY//Z
---

Over the past three years, I have had the privilege, as a highschool (now university) student, to contribute to a nationwide educational satellite program. The Peregrinus experiment, a collaboration among Flemish, Walloon, and Brussels high schools, was launched on the maiden flight of Ariane 6 ([VA262](https://en.wikipedia.org/wiki/Ariane_flight_VA262)), led by project coordinator **Erik de Schrijver**.


![Ariane 6 payloads](peregrinus_ariane6.jpg){: width="500"}
_Peregrinus experiment on the maiden flight of the Ariane 6 (VA262) marked with a red circle. Distributed with permission._

The objective was to measure the radiation and magnetic fields present around the Earth. Together with Roman Vannieuwenhuyse, I worked on the mission's software more specifically with regards to the communication downlink through the Iridium constellation network.

The experiment’s payload was built around an **Atmega328** microcontroller performing readout of the sensors and transmission of the payload data. The sensors used were an **X100-7** radiation detector, an **LSM9DS1** inertial measurement unit, and a **Rockblock 9603N** Iridium modem. Each sensor device had to be remain within strict power limits and data rates, which required careful adjustment of sampling intervals and data packet sizes.


![Peregrinus shaker table](shaker_table.jpg){: width="500"}
_Peregrinus experiment on shaker table at the Royal Military Academy (Brussels). Credits to Dirk Geeroms._


My role focused on developing the communication sub-program and its integration within the main flight software to ensure reliable data transfer through the [Iridium network](https://en.wikipedia.org/wiki/Iridium_satellite_constellation), fitting as much sensor data as possible into the 340-byte limit for short burst transmissions and ensuring the system can't crash due to transmission errors by adhering to *[The Power of 10: Rules for Developing Safety-Critical Code](../../assets/posts/peregrinus/P10.pdf)* developed by the NASA Jet Propulsion Lab. Coordination between teams proved essential, especially in managing version control and cross-checking hardware behavior.


The Peregrinus payload underwent vibration testing at the **Royal Military Academy** in Brussels and thermal-vacuum testing at the **ESA CubeSat Support Facility (CSF)** in Transinne, Belgium. These tests simulated the conditions the satellite would experience in orbit, including thermal cycling, vacuum exposure, and vibrational stresses. These tests verified the resonance behaviour, material integrity, and thermal performance of the payload under realistic orbital conditions.


![Peregrinus shaker table](peregrinus_thermal_vac_test.jpg){: width="500"}
_Peregrinus in thermal vacuum test chamber at the CubeSat Support Facility (CSF)._


On the 9th of July 2024, at 19:00 UTC, the Ariane 6 lifted off successfully from the Centre Spatial Guyanais in Kourou, French Guiana. Passing succesfully through the many phases of ascent, such as "*Max Q* " where the launcher vehicle experiences maximum dynamic pressure, it eventually reached a stable low Earth elliptical orbit (LEO) of approximately 300 km by 600 km. This launch marked the first flight of Europe's next-generation heavy-lift launch vehicle, being a major success for the European Space Agency and ArianeGroup.


{% include embed/youtube.html id='uCf-mN7ABWk' %}


During its mission, the launcher completed the deployment sequence, releasing the fairing and a range of cubesats, exposing the static scientific and educational payloads. But regretfully our experiment failed to transmit any packets, we hypothesize that was due to the long-term stability of the battery system, losing the battery charge before launch.

Participating in this mission and working together as team will remain a core memory of mine for many years to come, and I look forward to new opportunities to contribute to space research and cubesat missions.

For a detailed overview of the Peregrinus experiment, read the [ESA mission article](https://www.esa.int/Enabling_Support/Space_Transportation/Ariane/Ariane_6_launches_Peregrinus_students_take_on_the_Sun); for general information about the launch, read the [ESA mission overview](https://www.esa.int/Enabling_Support/Space_Transportation/Ariane/Europe_s_new_Ariane_6_rocket_powers_into_space).