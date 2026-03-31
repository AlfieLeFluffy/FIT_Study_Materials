---
tags:
  - FYO
aliases:
  - diffraction
sources:
  - "[[FYO_03_Difraction.pdf]]"
---
Diffraction is the bending (curving) of light around edges. This is the result of the wave nature of light as with [[Interference|interference]] and [[superposition]]. This means that light can around objects and into the geometric shade of the object. This is caused by the **Huygens' princip**, which states that each point of the wave-front is a point source of the wave itself. 
We divide the outcoming diffraction from a point hole or edge by the distance we observe it in. Within close range of the edge we call it **Fresnel diffraction** and then at a bigger distance we call it **Fraunhofer diffraction** (a special case of Fresnel diffraction). 
## Fraunhofer Diffraction
### 1D Hole
Onto a 1D hole of size $a$ fall monochromatic planar wave of wavelength $\lambda$, with wave number $k=\frac{2\pi}{\lambda}$ and there is no phase shift along the hole. After the hole under an angle $\beta$ (which is taken between the perpendicular axis of the hole and the diffracted wave) coming from an elementary area of length $ds$ we get a path shift $\sigma=s\sin(\beta)$ and phase shift $\phi=ks\sin(b)$. The amplitude is proportional to the size of the zone $ds$ so that $Ads$. The complex amplitude of coming from the zone with width $ds$ is: $$dU=Ads\exp(-j\phi)=Ads\exp(-jks\sin(\beta))$$
If we take $x=\frac{1}{2}ka\sin(\beta)$ then the intensity in the direction $\beta$ is: $$I=UU^*=I_{0}\left( \sin \frac{x}{x} \right)^2$$
where $I_{0}=I_{max}=I(\beta=0)$. Minimums of intensity will occur for $\sin(x)=0$, so it means that for $x=\pm m\pi$, which results in $\pi a\sin(\beta) /\lambda = m\pi$ and the condition for minimums is then: $$a \sin(\beta)=m\lambda$$
### Grid
A grid is a construction of holes with distance of centres of holes $d$ and size of holes $a$. The interference maximums for a grid with phase shift $\phi=\pm_{2}m\pi$ the position of maxims on the backdrop will be: $$d\sin(\beta)=m\lambda$$ where $\beta$ set the position of the maximum and $m$ the rank of the maximum.
The division of light intensity coming through a grid is based on two components. The first is the interference member and the second one is the diffraction member and it looks like: $$I=I_{0}\left( \frac{\sin(M\beta /2)}{\sin(\beta) /2} \right)^2\left( \frac{\sin(\alpha)}{\alpha} \right)^2$$ where $\beta=\frac{\pi d}{\lambda}\sin(\theta)$ and $\alpha=\frac{\pi a}{\lambda}\sin(\theta)$. The first parenthesis is the interference member and the second is the diffraction member. This spectrum is symmetrical around the perpendicular center axis.
The grids themselves can be done in two ways, the first is transmission grating, which is holes in a thin material and reflection grating, which are saw teeth pattern mirrors.
### 2D Rectangle
A rectangle hole lies in a plane $(x,y)$. A planar monochromatic light falls upon from the axis $z$. Elements of the hole $dxdy$ influence to the complex amplitude of the diffracted wave in the direction set by direction cosines $lmn$ have the same amplitude $Adxdy$ but different phase. The path shift is $\sigma=lx+my$, which results in a phase shift $\phi=k\sigma=k(lx+my)=k_{x}x+k_{y}y$ where $k_{x}=lk$ and $k_{y}=mk$. 
The sum of parts can be expressed as: $$U(l,m)=\int \int A\exp\left( -j 2\pi\left( l \frac{x}{\lambda}+m \frac{y}{\lambda} \right) \right)dxdy$$ or: $$U(k_{x},k_{y})=\int \int A\exp(-j 2\pi(k_{x}x+k_{y}y))dxdy$$
For a rectangle hole of width $2a$ and height $2b$ it is: $$U(k_{x},k_{y})=A\int_{-a}^a\int_{-b}^b \exp(-j 2\pi(k_{x}x+k_{y}y))dydx=4abA \frac{\sin(k_{x}a)}{k_{x}a}\frac{\sin(k_{y}b)}{k_{y}b}$$
### Common 2D
The 2D rectangle function has a more common application. This relays on the fact that we can express the amplitude as a function $A(x,y)$ depending on the position within the hole, which gives us a common **aperture function**: $$U(k_{x},k_{y})=\int \int_{\text{Aperture}}A(x,y)\exp(-j 2 \pi (k_{x}x+k_{y}y))dxdy$$
### Circular Aperture
In the common 2D aperture function we can input $A=1$ for aperture space $x^2+y^2=\rho^2<(D /2)^2$. After some simplifications we get intensity $I(\rho)$, which is given by the function: $$I(\rho)=I_{0} \frac{2J_{1}(\pi D\rho /(\lambda d))}{\pi d\rho /(\lambda d)}$$ where $\rho=\sqrt{ x^2+y^2 }$, $D$ is the diameter, $d$ is distance to the backdrop and $J_{1}(z)$ is a Bessel function (first rank) of argument $z$. The diffraction image is called **Aireys's image**, with a central circle called an **Aireys's disk** that has the angle radius: $$\Phi=1,22 \lambda /D$$
The Aireys's disk contains $84\%$ of incoming light, the first and second disks contain $91\%$ of light and this continue one with the rest.
### Resolution
We can say that to observe a point object within an optical system/device or by eye is always an Aireys's diffraction image, because there is always a bounding circular aperture. To figure out the resolution boundaries we can use the **Rayleigh's criterium**, which states that two points can be differentiated between when the maximum of the Aireys's disk of the first point lies within at least the minimum of the diffraction image of the second point. For this we use the Aireys's disk angle radius formula: $$\Phi=1,22 \lambda /D$$
## Spectroscopes
Spectroscopes are devices that analyse incoming light by dividing it into its spectral components. This is most often done through a some kind of grid diffraction. 
The basic construction of a grid spectrometer is:
- A light source to be analysed.
- A lens to focus the light
- A collimator with a hole in the front
- A grid at the end of the collimator output
- A telescope to observe the output of the grid under an angle
The observable output of the spectroscope is the light components that made up the original input light. A simple version of this kind of spectroscopes can be created with a CD or DVD, cereal box and some aluminium foil.