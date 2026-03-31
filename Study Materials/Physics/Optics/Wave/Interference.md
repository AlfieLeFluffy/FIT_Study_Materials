---
tags:
  - FYO
aliases:
  - interference
sources:
  - "[[FYO_02_Interference.pdf]]"
---
Interference is based on the princip of **[[superposition]]**, where the wave functions can be summed up. [[Superposition]] of electromagnetic light occurs if at a given point there are two or more light waves meeting. The basic formula is: $$U(\vec{r},t) = \sum U_{i}(\vec{r},t) = U_{1}(\vec{r},t)+ U_{2}(\vec{r},t)+ \dots$$
The interference can be either **constructive** or **destructive**.
### Intensity
The **intensity** of the resulting [[superposition]] wave is based on the intensity of the waves and their **phase diference**, such that: $$I(\vec{r})=U(\vec{R}).U^*(\vec{r})$$
Interference causes the spatial redistribution of intensity. The law of energy conservation is not broken here. Optical interferometers are based on the interference of two waves. An important thing to keep in mind is the **wave coherence condition**.
A observable result of [[superposition]] (interference) is only observable for coherent waves of which the phase shift (difference) is constant.
### Two Waves
For the interference of coherent planar two waves $U_{1}(\vec{r})=a\exp(j\phi_{1}(\vec{r}))$ and $U_{2}(\vec{r})=a\exp(j\phi_{2}(\vec{r}))$ with intensity is $I_{1}=U_{1}.U_{1}^*=a^2=I_{2}$:
- Superposition of waves: $U(r)=U_{1}(r)+U_{2}(r)$
- Intensity: $$I=UU^*=(U_{1}+U_{2})(U_{1}^*+U_{2}^*)=U_{1}U_{1}^*+U_{2}U_{2}^*+U_{1}^*U_{2}+U_{1}U_{2}^*$$$$=a^2(1+1+\exp(j(\phi_{2}-\phi_{1}))+\exp(-j(\phi_{2}-\phi_{1})))=I_{1}+I_{2}+2\sqrt{(I_{1}I_{2})^*}\cos(\phi_{2}-\phi_{1})$$
- The **interference equation**: $I=I_{1}+I_{2}+2\sqrt{(I_{1}I_{2})^*}\cos(\phi_{2}-\phi_{1})$
- The **interference element**: $2\sqrt{(I_{1}I_{2})^*}\cos(\phi_{2}-\phi_{1})$
- The expression $\phi=\phi_{2}-\phi_{1}$ is the **phase shift** (difference).
- The relation between phase shift and path shift $\delta$ is $\delta / \lambda = \phi / 2\pi$
The interference equation can also be interpreted geometrically using a phase diagram, which shows that the size of the phasor $U$ is sensitive to phase shift and not only to the size of the creating phasors.
If the intensity of both waves are the same $I_{1}=I_{2}=I_{0}$ then we can simplify the interference equation into $I=2I_{0}(1+\cos(\phi_{2}-\phi_{1}))$.
We can also define the for what **phase and path shifts** occurs with **constructive and destructive interference**:
- **Constructive**: $\phi=0,\pm 2\pi, \pm 4\pi, \dots$ and $\delta=\phi^*\lambda / 2\pi=0, \pm \lambda, \pm 2\lambda$
- **Destructive**: $\phi$ is equal to the odd multiplication $\pm (2m-1)\pi$ and $\delta=\pm (2m-1) \lambda/2$
### M Waves
Interference of $M$ coherent waves with the same amplitude and same phase shift $\phi$. Complex amplitude of each wave is $U_{m}=\sqrt{ I_{0} }\exp(-j(m-1)\phi)$ for $m=1,\dots,M$. The final complex amplitude will be $U=\sum_{m=1}^M Um$.
The final intensity will be $I=U.U^*=I_{0}\left( \frac{\sin(M\phi / 2)}{\sin(\phi /2)} \right)^2$.
### Planar Waves with Angle
For the interference of two monochromatic planar waves with the angle $\theta$ between them it generally applies that: $$u(\vec{r},t)=a\cos(\omega t-\vec{k} \vec{r} )=a\cos(\omega t-(k_{x}x+k_{y}y+k_{z}z))$$ and the complex amplitude is: $$U(\vec{r})=I^{1/2}\exp(-j\vec{k}\vec{r})=I^{1/2}\exp(-j(k_{x}x+k_{y}y+k_{z}z))$$
Two coherent planar waves with the same intensity $I_{0}$ are spreading along the plane $(x,y)$:
- One wave is spreading along axis $z$, $k_{z}=k$ and $U_{1}=I_{0}^{1/2}\exp(-jkz)$
- Second wave has an angle $\theta$ with $z$, $k_{x}=k\sin(\theta)$, $k_{z}=k\cos(\theta)$ and $U_{2}=I_{0}^{1/2}\exp(-jk(z\cos(\theta)+x\sin(\theta)))$
At point $z=0$ the phase difference is $kx\sin(\theta)$, which is a function of $x$. Interference element is then $2I_{0}\cos(kx\sin(\theta))$. Constructive interference occurs for $kx\sin(\theta)=2\pi m\to x=m\lambda /\sin(\theta)$. The interference image is periodic and the period is $\lambda / \sin(\theta)$.
### Planar and Spherical
The interference of a:
- **spherical**: $U_{1}=A_{1} / z \exp(-jkz)\exp(-jk(x^2+y^2) /2z)$
- **planar**: $U_{2}=A_{2}\exp(-jkz)$
with the interference element $2\sqrt{ I_{1}I_{2} }\cos(\phi)$ and phase shift $\phi=arg(U_{2})-arg(U_{1})$$=-kz-(-kz-k(x^2+y^2) /(2z))$ creates constructive interference for $\phi= \pm_{2}\pi m$ in plane $z=d$ if the condition $2\pi m=k(x^2+y^2) /2d$ is met.
This creates circles on the interference image of the radius $R=2\sqrt{ m\pi d /k }=\sqrt{ 2md \lambda }$.
## Young's Experiment
Two coherent spherical waves, that are coming out of close points $P_{1}$ and $P_{2}$ (small holes) interferant on a backdrop place at a distance $d$, creating an interference image.
- Wave coming from point $P_{1}=[-a,0,0]$: $\frac{A}{z}\exp(-jkz)\exp\left( -j \frac{k}{2z}((x-a)^2+y^2) \right)$
- Wave coming from point $P_{2}=[+a,0,0]$: $\frac{A}{z}\exp(-jkz)\exp\left( -j \frac{k}{2z}((x+a)^2+y^2) \right)$
The phase shift is: $\phi=\phi_{2}-\phi_{1}=\frac{2xak}{z}$.
For the distance of the backdrop $z=d$ is for the wave count $k=2\pi \lambda$ is the phase shift the same for both waves equal $\phi=4\pi xa /\lambda d$. Interference element is $\sqrt{ I_{1}I_{2}\cos(2\pi xa /\lambda d) }$. Constructive interference occurs for $4\pi x_{m}a /\lambda d=2\pi m$ where $m$ is a whole number. This means that the white interference lines on the backdrop are in Young's experiment set by the condition $$x_{m}=m \lambda d / 2 a$$ and the distance of the lines is $\lambda d / 2 a$.
The **phase shift** is caused by a **path shift** $\Delta L$ of the waves: $$\Delta L = d \sin(\theta)$$
The position of the **maxims** (constructive interference, white lines) is: $$\Delta L = m \lambda\to d\sin(\theta)=m\lambda$$
The positions of the **minims** (destructive interference, black lines) is: $$\Delta L=(2m-1) \frac{\lambda}{2} \to d\sin(\theta)=(2m-1) \frac{\lambda}{2}$$
## Interferometers
There are two kinds of interferometers, which are **linear interferometers** and **non-linear interferometers**.
### Linear Interferometers
A linear interferometers is an optical device, that splits a wave into two rays, usually called **reference** and **measured**. These rays then go through different paths or environments and then are connected back together into one wave that is measured on a sensor. As a result/during this we can measure the intensity of the resulting wave created by the [[superposition]] of the two split beams.
To split the light we often use a semi-transparent mirrors (splitters) and mirrors.
#### Michelson's Interferometr
Uses a beam splitter to split incoming light into two sections. The first is a reference beam that is routed towards the mirror $M_{1}$ through a correction optic $d_{1}$. The second beam is direct towards the mirror $M_{2}$. We can move the mirror $M_{2}$ or rotate it, creating differing light paths which results in a different light interference image on the sensor once both beams merge back together. The interference equations for this is: $$I=2I_{0}(1+\cos(2\pi \sigma / \lambda))$$ Notably, if we move the mirror $M_{2}$ by $\lambda /4$ then the resulting path difference is $\sigma = 2d = 2 \frac{\lambda}{4}=\frac{\lambda}{2}$.
#### Mach-Zander Interferometer
Uses a beam splitter to once again split incoming light into two beams: **reference** and **measured**. Unlike with the **Michelson's** this interferometer does not reflect the light back into the same beam splitter, but uses two different paths and mirrors at the end of those paths to reflect the light into another beam splitter that combines the beams together and directs them towards a detector. This can also be expanded to include a second detector for the light reflected towards the perpendicular way.
The two paths contain one cell each. Into the measured path we can insert an object, light source, etc, that is to be measured and the reference path contains a corrective (compensating) optic.
These interferometers are used in high speed data transfers for fibber optics, datacentres, lab-on-chip sensors, etc.
#### Fabry-Perot Interferometer
An interferometer based on two plan-parallel mirrors that are separated by an air gap. The distance between the mirrors is adjustable with width $d$.
This is used with divergent light (coming form an area light source or a divergent laser beam). Between the mirrors occurs repeated reflection of waves and a multibeam interference occurs where the maximums of permeability happen only in specific places that depend on the wavelength and distance $d$.
Another way to think about this is as of interference of infinite amount of monochromatic waves with lower amplitude and a constant phase shift. If we use a lens to gather the output we can create an interference image of consecutive rings. The condition of interference maximum for this image is: $$m \lambda=2d n_{d} \cos(\theta)$$
These interferometers are used in spectroscopic devices, filters with limited bandwidth, etalon, etc.
## Interference on Thin Layers
The **phase shift** during interference on a thin layer occurs due to:
- Spreading of waves through an environment of a different **refraction index**.
- Spreading of waves in **differently long paths** (usually if the path differs $\sigma=m\lambda$ then it is constructive interference).
- **Reflection** on the surface.
The parameters of the thin layer are **refraction index** $n$ and **width** $d$. It applies that: $$2AB=2d /\cos(\theta_{t}),AC=2d \sin(\theta_{t}) / \cos(\theta_{t}), \dots$$
The condition of constructive interference on a thin layer is: $$\sigma=m\lambda=2nd \cos(\theta_{t})$$ and applies between thinner and thicker interfaces, such as an oil layer on water, otherwise it is explained through electromagnetic optics.
## Interference Filters
The goal of interference filters is to let through a thin interval of wavelengths and the supress the rest. This is usually done on the princip of **Fabryu-Perot interferometer**, where two very thin transparent metallic layers separated by a layer of some dielectric material with the width of $d$ and the condition $m\lambda=2nd$, $m=1$ or $m=2$. This is called a MDM filter.
Another use is in antireflexive finishes.
Interference filters can also be done as multilayer filters, such as in mirrors for lasers, camera lenses, etc. They have a alternating layers materials with different **refraction indexes** and width $\frac{\lambda}{4}$. These filters can covers a wide range of wavelengths from the infrared to the ultraviolet.