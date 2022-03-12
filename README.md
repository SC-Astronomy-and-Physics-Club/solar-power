# Solar Flux for the 21-cm Line
Written by Austin Lake

Saddleback College, Mission Viejo

## Introduction
This Jupyter Notebook calculates the expected solar flux at the 21-cm line, as observered from Saddleback College's 2-meter radio telescope

## Method
First, the radiance of the Sun at an estimated temperature of 5778 K, is dervied used Planck's Law of blackbody radiation. This derivation outputs units of Watts per meter-squared per sterradian [W/m^2/sr]. Because the Sun lies within the FOV of the telescope, the solid angle [sr] is calcuated from a point behind the radio telescope that propagates outward toward the Sun. The center axis of propagation passes through the both the center of the dish and the center of the Sun. Additionally, the outside edges of this solid angle form a tangent line on the edge of the dish and the meridian of the Sun that is perpendicular to the axis of propagation. The radiance from the blackbody model is then multiplied by the solid angle and the telescope's aperature area [m^2] to get the flux [W]. This is then converted to fit a logrithimic scale, resulting in units of decibel milliwatt [dBm].

## Solid Angle Relationship
![](solidAngle.png)

### Derving the Solid Angle of Our Dish and the Sun
$\Omega=\frac{A}{r^2}, 0\leq\Omega\leq 4\pi, r=\mathrm{radial\space distance}$

$\Omega=\frac{A_{dish}}{X^2}, A_{dish}=\mathrm{apeture}, X=\mathrm{radial\space distance\space to\space dish}$

$\Omega=\frac{A_{sun}}{(au + X)^2}, A_{sun}=\mathrm{hemisphere\space of\space Sun\space facing\space dish}$

$\frac{X^2}{A_{dish}}=\frac{(au+X)^2}{A_{sun}}$

$\frac{X^2}{A_{dish}}=\frac{\mathrm{(au)^2+2au(X)+X^2}}{\mathrm{A_{sun}}}$

$(\frac{1}{A_{dish}}-\frac{1}{A_{sun}})x^2-\frac{2au}{A_{sun}}X-\frac{(au)^2}{A_{sun}}=0$

$a=\frac{1}{A_{dish}}-\frac{1}{A_{sun}}=\frac{1}{2\pi (D_{dish})^2}-\frac{1}{2\pi ((r_{sun})/2)^2}=\frac{1}{\pi ((4.5\space m)/2)^2}-\frac{1}{2\pi (695700000.0\space m)^2}=0.06287602690050187$

$b=-\frac{2au}{A_{sun}}=\frac{2au}{2\pi (r_{sun})^2}=\frac{149597870700.0\space m}{\pi (695700000.0\space m)^2}=-1.967711973475555E-07$

$c=-\frac{(au)^2}{A_{sun}}=\frac{(au)^2}{2\pi (r_{sun})^2}=\frac{(149597870700.0\space m)^2}{2\pi (695700000.0\space m)^2}=-14718.276069141897$

$X=\frac{-b+\sqrt{b^2-4ac}}{a^2}=\frac{-(-1.967711973475555E-07)+\sqrt{(-1.967711973475555E-07)^2-4(0.06287602690050187)(-14718.276069141897)}}{(0.06287602690050187)^2}=\mathrm{483.82235182348757\space m}$

$\Omega=\frac{A_{dish}}{X^2}=\frac{\pi (D_{dish}/2)^2}{X^2}=\mathrm{\frac{\pi (4.5\space m/2)^2}{(483.82235182348757\space m)^2}=0.00013588547880587752\space sr}$
