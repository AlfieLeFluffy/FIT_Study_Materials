---
tags:
  - FYO
aliases:
  - progressive waves
sources:
  - "[[FYO_01_Waves.pdf]]"
---
To create progressive waves we can move an element of a flexible environment from its resting position and the release it. By the influence of the flexible forces within the environment it starts to oscillate. The interconnectivity of the flexible environment forces other near by elements to also oscillate. This creates a excitement within the environment, which is called a wave.
No elements are moved by the wave, but oscillate through around their stable calm position. There is transference of energy, momentum, but not material.
A progressive wave can be described by a **wave function** $u(z,t)=f(t-z/c)$.
## Wave Function Constructions
At point $z=0$ we have a generating function $u(t)$ with a time deviation variable $t$. The same deviation will have a point with position $z$ after $\tau=z/c$. This results in equations:
$$u(z=0,t)=u(t)$$
$$u(z,t)=u(t-\tau)=u(t-z/c)$$
where $c$ is the speed by which the **phase** travels (phase velocity). Any function that satisfies the argument $t-\tau / c$ is a wave function. The argument $t- z / c$ is called the **wave phase** $\phi$. This is different from the term **phase difference**, which is $\phi_{2}-\phi_{1}$.
## Harmonic Wave Monochromatic
A wave function generating in point $z=0$ is $u=u_{m}\cos(\omega t)$, which is a function with period $T$. The wave function $u=u_{m}\cos(\omega(t-z /c)+\phi_{0})$ has amplitude $u_{m}$, starting phase $\phi_{0}$. This function has both time $T$ and space periods $\lambda$.
- **Space variables**
	- The wave length is $\lambda=cT$
	- The wave number is $k=2\pi / \lambda$
- **Time variables**
	- The frequency is $v = 1 / T$
	- The angle frequency is $\omega=2\pi v$
So after some updates the final wave function is: $$u=u_{m}\cos(\omega t-kz) = u_{m}\cos(2\pi(t / T - z / \lambda))$$
Another variable that can be used is the **phase velocity** or in other words how quickly does the phase spreads. The basic equation for this is: $$c=\frac{\omega}{k}=\frac{\lambda}{T}$$
## Pulses
Pulses are non-periodic waves. There are two notable pulses to keep in mind and those are:
- **Lorence pulse**
	- $u(z=0,t)=a/(t^2+1)\to u(z,t)=a / ((t-z /c)^2+1)$
- **Gaussian pulse**
	- $u(z=0,t)=a \exp(-t^2)\to u(z,t)=a \exp(-(t- z /c)^2)$
## Wave-Front Waves
A **planar wave** that is perpendicular to the direction of spreading has the same phase and so also the same difference. We are moving the direction of a unit vector $\vec{n}$, $\vec{k}=k \vec{n}$ is the wave vector. A planar wave has thus the wave function: $$u=u_{m}\cos(\omega t-\vec{k}\vec{r})$$
If we insert into direction $\vec{k}$ the place $(z)$ then it become: $$u=u_{m}\cos(\omega t-kz)$$
A **spherical wave** has the following equation instead: $$u(r,t)=\frac{A}{r}\cos(k(ct\pm r))$$
## Wave-Front and Rays
A **wave-front** is an area on which the oscillating elements have the same phase. A **ray** is a curve that is in all positions perpendicular to the **wave-front** and points towards the direction of the wave movement.
## Complex Number Representation
A wave function can be represented through [[Complex Number|complex number]] using a complex number version of the wave function. This is done to simplify calculations with wave functions. This means that we can take the harmonic monochromatic wave function: $$u(z,t)=u_{m}\cos(\omega t-kz)$$ and then use the Euler's relation $\exp(i\phi)=\cos(\phi)+i\sin(\phi)$ and we can rewrite the original function into: $$u(\vec{r},t)=\mathrm{Re}(u_{m}\exp(j(\omega t-\vec{k}\vec{r})))=\mathrm{Re}(U(\vec{r},t))=\frac{1}{2}(U(\vec{r},t)+U^*(\vec{r},t))$$
The real harmonic wave function $u(\vec{r},t)$ is the real component of the complex function. A common definition is then: $$U(\vec{r},t)=a(\vec{r})\exp(j\phi(\vec{r}))\exp(j\omega t)$$ where the complex amplitude $U(\vec{r})$ is: $$U(\vec{r})=a(\vec{r}\exp(j\omega(\vec{r})))$$
It is a complex number where the size $|U(\vec{r})|$ is the **amplitude** of the wave and the argument $arg(U(\vec{r}))$ is the **phase**. The intensity of the wave is then $$I(\vec{r})=U(\vec{r}).U^*(\vec{r})=|U(\vec{r})|^2$$ where $U^{*}(\vec{r})=\text{conj}(U(\vec{r}))$.
## Parabolic Wave
Parabolic wave function is the replacement of spherical wave function $U(r)=A / r\exp(-jkr)$ by two members of the **Taylor expansion** (series), which is: $$U(r)=A /r \exp(-jkr)=A /z\exp(-jk(x^2+y^2) /2z)\exp(-jkz)$$