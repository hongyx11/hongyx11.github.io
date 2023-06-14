---
title: High Performance Soft/Hard Real-time Controller for Ground-based Telescopes 
summary: Computational Astronomy Project Website
tags:
  - computational astronomy
date: '2022-10-11T00:00:00Z'

# Optional external URL for project (replaces project detail page).
external_link: ''

image:
  caption: Figures from [web](https://www.forbes.com/sites/startswithabang/2018/03/22/5-reasons-why-astronomy-is-better-from-the-ground-than-in-space/?sh=4489bf5348f8)
  focal_point: Smart

links:
url_code: ''
url_pdf: ''
url_slides: ''
url_video: ''

---
Our knowledge of the universe will make a giant leap as the largest ground-based
telescopes, with diameters of 25 to 40m~\cite{main-elt,main-ltao-gmt}, 
see first light before the end of this decade. They will provide the
angular resolution and collecting area required to detect the first stars and first
galaxies as well as faint rocky exoplanets around other stars, possibly harboring life.
However, they must overcome optical distortions caused by air turbulence 
in order to achieve the needed resolution and contrast.
To compensate for such distortions, Adaptive Optics (AO) 
technologies
were developed for astronomy more than 30 years ago, and are now essential components
for most of the optical telescopes currently in operation~\cite{Hardy1977}. 
In its simplest form, an AO system is composed of
a Wavefront Sensor (WFS) used to measure atmospheric distortions at a high frame rate,
which are then compensated with a Deformable Mirror (DM). The sub-system responsible
for interpreting wavefront measurements into actual commands to actuators is the Real-Time
Controller (RTC). 
It must operate at high speed (i.e., kHz rate) to keep up with the rapidly
changing optical turbulence. Most importantly, since AO is usually arranged in a closed
loop setting, time-to-solution must be reliably at the level of a fraction of
the operating rate (few tens of $\mu$s) to ensure stable behavior for this loop.

Wavefront sensing and actuator commands retrieval are based on modeling of the AO system 
error budget and solved with a linear control system,
sometimes regularized with a given prior on the turbulence statistics. For instance,
in present-day conventional AO systems, the RTC 
follows a scheme in which input measurements 
from sensors are reduced into a measurement vector which
is multiplied by a control matrix to produce an output DM control vector of 
commands~\cite{Madec1999}. 

Other instruments are coupled with the AO module, as for example
an imager or a spectrograph. Observations are usually carried out at wavelengths
ranging from 1$\mu$m to 5$\mu$m, i.e., the Infrared (IR) window of the atmosphere, where the
transmission is high, and for which AO systems deliver their best performance.
Extending AO coverage to shorter optical wavelengths (i.e., below 1$\mu$m) is a
challenge because it requires wavefront correction on very short spatial and temporal
scales. While designing systems with a larger number of actuators and a faster response
time is not that challenging conceptually, realizing these conceptual designs in practice
is problematic because they demand exquisite stability, ultra-precise wavefront
reconstruction and flawless sub-systems calibration.

One of the limitations of classical AO is that the correction is only valid in a
very small patch of sky, the size of which depends on the observing wavelength,
from a few arcsec in the visible to a few tens of arcsec in the near IR. Multi-Conjugate Adaptive
Optics (MCAO) solves this problem by using a series of DMs to compensate the turbulence
in volume, enabling AO correction over a wide field of view (FoV)~\cite{Beckers1989}. 
MCAO uses several
guide stars and associated WFSs to probe the light wave aberrations in several directions,
and an RTC using tomographic reconstruction determines the best commands to apply to the DMs. 
In this case, the control matrix is often called the tomographic reconstructor~\cite{Vidal2010}. 
Figure~\ref{fig:mcao} depicts the principle of MCAO in a very simple configuration with only 
2 WFS and 2 DMs. 


[spack]({{< relref "/post/spackinstall" >}})
