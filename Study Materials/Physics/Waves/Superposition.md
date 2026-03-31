---
tags:
  - FYO
aliases:
  - superposition
sources:
  - "[[FYO_01_Waves.pdf]]"
---
## Superposition
A superposition is the concept that two waves traveling in different directions and with different phases do not interfere with one and another and the resulting intensity in a given time and place is their sum. We can note it as: $$u(z,t)=u_{1}(z,t)+u_{2}(z,t)$$
In all we can say that:
- The algebraic difference of overlapping waves are summed into one wave.
- Overlapping waves do not interfere with one another during spreading.
### Still Waves
Still waves are the result of two identical waves that are spreading directly against each other. They can be written as: $$u(z,t)=u_{m}\sin(\omega t-kz)+u_{m}\sin(\omega t+kz)= 2u_{m}\cos(kz)\sin(wt)$$
An interpretation of this outcome can be that each element of the environment with coordinates $z$ does a harmonic movement with amplitude $2u_{m}\cos(kz)$. These waves can be found in:
- Optical resonators
- Musical instruments
- Weiner's experiment
### Weiner's Experiment
Still electromagnetic waves in the visible spectrum can be visible under specific conditions. There are three components:
- A mirror
- A photosensitive film with width $\alpha=\frac{\lambda}{20}$
- Light
The idea is that if the film and mirror are placed at an incredibly low angle between each other, for example $\simeq 1\times 10^-3\text{ rad}$ and shine the light directly at the mirror, then we can observe black strips forming on the film. 
This is due to the light first going through the film, then bouncing back and forming still waves due to superposition on the film. The distance between each line should be $\lambda /2 /\sin(\alpha)$. This can be used in many applications, such as light lithography.
### Fourier Analysis
Superpositions of harmonic (sin functions) waves can be create a wave function of an an-harmonic nature. A [[Fourier Series]] can be used to describe a an-harmonic function $f(t)$ through periodical function with period $T$ as a series: $$f(t)=\frac{a_{0}}{2}\cos\left( m \frac{2\pi}{T}t \right)+\sum_{m=1}^{\infty}b_{m}\sin\left( m \frac{2\pi}{T} t\right)$$where $a_{m}=\frac{2}{T}\int_{0}^Tf(t)\cos\left( m \frac{2\pi}{T} t\right) dt$ and $b_{m}=\frac{2}{T}\int_{0}^Tf(t)\sin\left( m \frac{2\pi}{T} t\right) dt$. 
Using the exponential Euler equations is: $$f(t)=\sum_{m=-\infty}^\infty c_{m} \exp\left( jm \frac{2\pi}{T} t\right)$$ $$c_{m}=\frac{1}{2}(a_{m}-jb_{m})=\frac{1}{T}\int_{0}^T f(t)\exp\left( -jm \frac{2\pi}{T} t\right) dt$$
We can also extrapolate into the series a function of coordinates $g(z)$ with a space period. Non-periodic waves can thus be evaluated through Fourier transformation in the interval $(-\infty, \infty)$: $$f(t)=\int_{-\infty}^\infty F(v)\exp(-j 2 \pi vt) dv$$ $$F(v)=\int_{-\infty}^\infty f(t)\exp (-j 2 \pi vt) dt$$