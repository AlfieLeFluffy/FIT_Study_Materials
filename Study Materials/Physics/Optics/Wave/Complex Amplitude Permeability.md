---
tags:
  - FYO
aliases:
  - Complex amplitude permeability
  - complex amplitude permeability
sources:
  - "[[FYO_04_Holography.pdf]]"
---
An object of width $d(x,y)$ is defined by coordinates $z=0$ and $z=d_{0}$. An incoming planar wave is spreading along the axis $(z)$. We can define a **complex amplitude permeability** as a ration of complex amplitudes: $$\tau(x,y)=U(x,y,d_{0}) / U(x,y,0)$$
### Transparent Plate
A plane-parallel plate is placed in vacuum around the axis $(z)$. The surface of the plate is placed in coordinates $z=0$ and $z=d$. Onto the plate falls planar monochromatic wave in the direction of the axis $(z)$.
Through the plate the wave moves as a planar wave again, its amplitude is for $z=0$ equal to $U(x,y,0)=A$. For $z=d$ it is $U(x,y,d)=A\exp(-jnk_{0}d)$. The complex amplitude permeability of the plate is: $$\tau(x,y)=\exp(-jnk_{0}d)$$
The plate causes a phase shift $\phi=nk_{0}d=2\pi d /\lambda$.
### Two Transparent Plates
If we take two transparent plates that are tightly behind each other, then the complex amplitude permeability is: $$\tau(x,y)=U(x,y,d_{1}+d_{2}) / U(x,y,0)=\exp(-jn_{2}k_{0}d_{2})\exp(-jn_{1}k_{0}d_{1})=\tau_{2}\tau_{1}=\tau_{1}\tau_{2}$$
Both plates cause the phase shift $\phi=+k_{0}(n_{1}d_{1}+n_{2}d_{2})$.
### Transparent Plate of Variable Width
The permeability is calculated as a multiplication of permeability of a thin layer of air of variable width $d_{0}-d(x,y)$ and permeability of the thin transparent environment $d(x,y)$ and refraction index $n$. This is: $$\tau(x,y) \sim \exp(-jk_{0}(d_{0}-d(x,y)))\exp(-jnk_{0}d(x,y,))\to \tau(x,y)=h_{0}\exp(-j(n-1)k_{0}d(x,y))$$ where $h_{0}=\exp(-jk_{0}d_{0})$ is substantial **phase factor**. The plate cause phase shift of $\phi=(n-1)k_{0}d(x,y)$.
### Slice $f(x,y)$ through Planar Wave
In the context of planar monochromatic waves a common problem is finding the complex amplitude of the planar wave in point $z=0$, which is $U(x,y,0)=f(x,y)$ (slice through the wave). We can create $U(x,y,z)$ with the basic assumption that wavelength is $\lambda$ ($k=\frac{2\pi}{\lambda}$). The resulting equation is: $$U(x,y,z)=A\exp(-j(k_{x}x+k_{y}y+k_{z}z))$$ where $$k_{z}=\sqrt{ k^2-k_{x}^2-k_{y}^2 }=\sqrt{ (2\pi / \lambda)^2-k_{x}^2 -k_{y}^2 }$$
Importantly, if know the wave slice $U(x,y,0)$ and the wavelength $\lambda$ then we can reconstruct the wave $U(x,y,z)$.
A similar issue is found when a planar monochromatic wave of wavelength $\lambda$ ($k = 2\pi / \lambda$), spreading along the axis $(z)$ and going through an optical element with permeability: $$\tau(x,y)=\exp(-j(k_{x}x))$$
The permeability $\tau(x,y)$ is by the definition of wave slice coming out of an object: $$U(x,y,z) \sim \tau(x,y) A \exp(-j(k_{z}z)) = A \exp(-j(k_{z}z)) \exp(-j(k_{x}x))$$
$$ U (x,y,z) = A \exp(-jnk_{0}(z\cos(\theta)+x\sin(\theta)))$$
It becomes a planar wave with wave vector $k$ (elements $k_{x}=k\sin(\theta)$, $k_{y}=\sin(\theta)$, $k_{z}=k\cos(\theta)$). The angle $\theta$ ($\sin(\theta)=k_{x} / k$) is between the axis $(z)$.