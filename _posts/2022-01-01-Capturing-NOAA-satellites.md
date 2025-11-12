---
title: "Capturing NOAA satellite images"
description: "Receiving weather satellite images using an V-dipole and SDR dongle."
author: yves
date: 2022-06-16 12:00:00 +0200
categories: [Applied Physics, Satellite capturing]
tags: [sdr, radio, antenna, RF, science, physics, engineering, experiment, data processing]
pin: false
recent-project: true
math: false
mermaid: false
media_subpath: /assets/posts/noaa_satellites

image:
  path: NOAA_15_AMAZING.jpg
  alt: Satellite image captured from NOAA 15 satellite on 27/05/2022 at 9:43.
---

There are around 4852 active satellites currently orbiting the Earth. ([space.com](https://www.space.com/world-space-week-satellite-megaconstellations-threaten-astronomy)) 
Many of these satellites transmit signals in proprietary data formats making decoding these signals impossible without the knowledge of the format or decryption key. Luckily there are a few satellites that transmit their data in publicly known formats without encryption, such as the polar-orbiting NOAA-15, NOAA-18 and NOAA-19 satellites from the *National Oceanic and Atmospheric Administration*. These satellites transmit live weather images near 137 MHz using [Automatic Picture Transmission](https://www.sigidwiki.com/wiki/APT), showing cloud cover and weather phenomena like cyclones and volcanic ash plumes, see table 1 for exact frequencies.


<figcaption class="text-center pt-2 pb-2">
    Table 1: NOAA satellites and APT transmitting frequency
</figcaption>

| Satellite | Frequency    |
|------------|--------------|
| NOAA-15    | 137.62 MHz   |
| NOAA-18    | 137.9125 MHz |
| NOAA-19    | 137.1000 MHz |
{: .center-table .tiny-table}

Using the [Dipole antenna kit](https://www.rtl-sdr.com/using-our-new-dipole-antenna-kit/) from RTL-SDR.com together with the [RTL-SDR v3](https://www.rtl-sdr.com/buy-rtl-sdr-dvb-t-dongles/) USB dongle it is possible to receive these satellite radio signals. The RTL-SDR is a type of **Software Defined Radio (SDR)**, a device that digitizes radio signals so that they can be processed, decoded, and analyzed entirely in software rather than relying on traditional radio hardware. Since the NOAA satellites broadcast at a frequency of around 137 MHz (corresponding to a wavelength of approximately 2.19 m), the dipole antenna should be configured accordingly. Extending each antenna arm to a length of about 53.4 cm and positioning them in a "V" shape, oriented toward the south, allows for optimal reception.



![V dipole](V-dipole.png){: width="400" }
_137MHz V-dipole antenna setup from [9A4QV](https://lna4all.blogspot.com/2017/02/diy-137-mhz-wx-sat-v-dipole-antenna.html)._


With an SDR dongle and the [SDR++](https://www.sdrpp.org/) utility, incoming analog radio signals are converted into digital data, which can then be demodulated and processed to retrieve the data within. This program allows for easily changing the listening frequency and also performs an Fourier transform to visualize the digital data in function as a so called "waterfall".

![SDR++ waterfall](waterfall.png){: width="600" }
_SDR++ program showing the waterfull._

Using [Gpredict](https://oz9aec.dk/gpredict/), an open-source real-time satellite tracking software, makes it easy to determine when a NOAA satellite will pass overhead. The software provides detailed information about upcoming passes, including the satellite’s elevation, azimuth, and duration of visibility. Using this tool, you can plan in advance when to setup the antenna and prepare for capturing the signals.

![Gpredict](gpredict.png){: width="700" }
_Gpredict application showing NOAA satellite's live location and reception areas._

To process the radio recordings, the [WXtoImg](https://www.wraase.de/wxtoimg/) program was used, this can extract the satellite image information from within the radio signals.

![WXtoImg](wxtoimg_example.png){: width="700" }
_WXtoImg processing an NOAA-18 recording._


Despite the careful setup, I did not immediately get good reception. Most recordings resulted in partial images with much noise (as can be seen below), likely due to my urban location and terrain reflections. 

| ![E-plane pattern](NOAA_18_10-47-14_04-03-2022.jpg){: width="480"} | ![H-plane pattern](NOAA_18_12-14-07_05-03-2022.jpg){: width="480"} |
{: .trans-table }
<figcaption class="text-center pt-2 pb-2  post-meta img_caption">
Partial NOAA-18 satellite images from 04/03 and 05/03 respectively.
</figcaption>

But after some attempts, an NOAA 15 passover was finally predicted to go straight overhead giving a long receiving window. This attempt produced an amazing sharp image of Central Europe showing the cloud cover as well as the cyclone above the Mediterranean sea. Below the image you can find a short fragment of the APT radio recording.

![NOAA 15 passover](NOAA_15_AMAZING.jpg){: width="700" }
_NOAA 15 satellite passover on 27/05/2022 at 9:43._



<div style="text-align: center;">
  <audio controls>
    <source src="../../assets/posts/noaa_satellites/NOAA_15_09-43-32_27-05-2022.mp3" type="audio/mpeg">
    Your browser does not support the audio element. :(
  </audio>
</div>

In conclusion, after some trial-and-error I was able to receive beautiful images of our Earth directly from weather satellites with budget-friendly radio equipment (around 40euros). I hope this post might be helpful to others who also want to capture these stunning images directly and are interested in radio technology.


Edit: As of August 2025 all active APT transmitting NOAA satellites are decommissioned (NOAA 15/18/19). We thank you for your service, you will be dearly missed. Per aspera ad astra.