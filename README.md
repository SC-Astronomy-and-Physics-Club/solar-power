# Solar Flux for the 21-cm Line
Written by Austin Lake

Saddleback College, Mission Viejo

## Introduction
This Jupyter Notebook calculates the expected solar flux at the 21-cm line, as observered from Saddleback College's 4.5 meter radio telescope

## Method
First, the radiance of the Sun at an estimated temperature of 5778 K, is dervied used Planck's Law of blackbody radiation. This derivation outputs units of Watts per meter-squared per sterradian [W/m^2/sr]. Because the Sun lies within the FOV of the telescope, the solid angle [sr] is calcuated from a point behind the radio telescope that propagates outward toward the Sun. The center axis of propagation passes through the both the center of the dish and the center of the Sun. Additionally, the outside edges of this solid angle form a tangent line on the edge of the dish and the meridian of the Sun that is perpendicular to the axis of propagation. The radiance from the blackbody model is then multiplied by the solid angle and the telescope's aperature area [m^2] to get the flux [W]. This is then converted to fit a logrithimic scale, resulting in units of decibel milliwatt [dBm].

### Flux Derivation

solid angle = Area/(radius)^2, A = source area (half of the Sun's surface area), radius = distance between Sun and dish

specific intensity = Planck's Law of Blackbody Radiation

flux density = specific intensity * solid angle

flux = flux density * frequency

power = flux * apeture

### Results

Specific Intensity (W/m^2/sr/Hz):	3.5815555594549246e-18 W / (Hz m2 sr)

Flux Density (W/m^2/Hz):		2.2503577268014545e-17 W / (Hz m2)

Flux Density (Jy):			2250357726.801454 Jy

Flux Density (sfu):			225035772680145.4 sfu

Flux (W/m^2):				3.196421058684347e-08 W / m2

Power (W):				5.083688038594618e-07 W

Power (dBm):				-32.93821107857174 dB(mW)

