---
tags:
  - FYO
aliases:
  - holography
  - holographs
  - Holographs
sources:
  - "[[FYO_04_Holography.pdf]]"
---
Holography is method of capture and reconstruction of 3 dimensional imagery and is based on on interference of highly coherent light. A recording of an object in a sensitive layer is called a hologram and holds information about intensity but also light phase created coming from the object. A hologram then also holds the way in which light has been reflected and defused on the object.
## Complex Amplitudes
A complex amplitude of a planar wave that has the wave vector in plane $(z-x)$ and with the axis $z$ holds the angle $\theta$ is: $$U(\vec{r})=U(x,y,z)=A\exp(-jnk_{0}(z\cos(\theta)+x\sin(\theta)))$$
A complex amplitude of a planar wave that is in the same direction as the axis $z$ is: $$U_{\vec{r}}=U(x,y,z)=A\exp(-jnk_{0}z)$$
A complex amplitude of paralax spherical wave is: $$U(\vec{r})=\frac{A}{z} \exp(-jnk_{0}z)\exp\left( -jnk_{0} \frac{x^2+y^2}{2z} \right)=a(\vec{r})\exp(-jnk_{0}z)$$ where $a(\vec{r})=\frac{Z}{z} \exp\left( -jnk_{0} \frac{x^2+y^2}{2z} \right)$ is the complex encapsulation. If its complex component is positive (negative) then the wave is divergent (convergent). If the wave has a center at $[x_{0},y_{0},z_{0}]$ then the complex encapsulation is: $$a(\vec{r})=a(x,y,z)=\frac{A}{z-z_{0}}\exp\left( -jnk_{0} \frac{(x-x_{0})^2+(y-y_{0})^2}{2(z-z_{0})} \right)$$
## Basic Princip
The direct photographic recording of the optical filed can only observe the optical intensity $|U(x,y)|^2$, but it is not able to capture the quickly changing phase of the wave that describes information about vector elements. Also other different recording devices do not react to the changing phase.
A way phase can be converted into intensity using [[Interference|interference]] of waves in the optical field (object waves $U_{0}$) and reference wave $U_{r}$ in axis $z=0$. So the holografy is a recording of intensity of the interference image of the object wave (optical field) and a reference wave. Reconstruction of the wave is then done from the saved wave and the reference wave.
Hologram is usually a thin optical element containing [[Complex Amplitude Permeability|complex amplitude permeability]] that is equal to the slice of the object wave in the axis $z=0$ ($\tau(x,y)=U_{0}(x,y)$). From the knowledge of wave length and permeability is it possible to reconstruct the object wave $U_{0}(x,y)$.
## Holographic Code
Intensity of the [[Interference|interference]] image created by the [[Superposition|superposition]] of the object and reference wave is recorded, usually into light-sensitive emulsion of photographic plate or film. In this way a transparent is created of which amplitude permeability is average of this intensity. It is a **hologram**. Hologram also contains additional information about the complex amplitude of the object wave $U_{0}$.
For the complex amplitude of the object wave $U_{0}=A_{0}\exp(j\phi_{0})$ and reference $U_{r}=A_{r}\exp(j\phi_{r})$. It applies that: $$\tau \sim (U_{0}+U_{r})\times(U_{0}+U_{r})^*=U_{0}U_{0}^*+U_{0}U_{r}^*+U_{0}U_{r}^*+U_{r}U_{r}^*=I_{0}+I_{r}+U_{0}U_{r}^*+U_{r}U_{0}^*$$
where $I_{0}$ respectively $I_{r}$ are intensities of object respectively reference waves. Hologram obviously contains information about size and phase of wave $U_{0}$. In places of maximums of dims is $\phi_{0}-\phi_{r}=2m\pi$ and in places of identical degree of dimming is $\phi_{0}-\phi_{r}=\text{const}$.
## Wave Reconstruction
To decode of the information within the hologram and to reconstruct the object wave, the same reference monochromatic wave is used. The hologram is exposed by the reference light. The wave of the modulated hologram is: $$U=\tau U_{r} \simeq I_{0}U_{r}+ I_{r}U_{r}+ U_{0}U_{r}U_{r}^*+ U_{0}U_{r}^*U_{r} = I_{0}U_{r} + I_{r}U_{r}+ U_{0}I_{r} + U_{0}^*U(r)^2$$
The third member on the right side is the original object wave (reconstructed), multiplied by a constant (intensity of the reference wave). The forth member is the conjuncted original wave modulated complex function $U_{r}^2$. The first two members do not contain any information about phase of the object wave.
About the reference wave we expect only that it is monochromatic and has the same parameters during recording or reconstruction. The reconstructed object field is [[Diffraction|diffraction]] of the reference wave on the hologram.