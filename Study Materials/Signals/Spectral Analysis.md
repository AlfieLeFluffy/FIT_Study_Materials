We use spectral analysis of signals to analyse their **frequential characteristic**. We are interested in:
- **Where** are the **frequential components** signal. On what frequencies these components are.
- **How many** signals there are on each frequency (**amplitude**).
- How is the signal on each frequency **shifted** (frequential phase).
We decompose signals into **sinuses** and **cosiness**. To convert signals from the timeline into a frequential decomposition, also known as **spectrum**, we use methods such as:
## Series
### Fourier Series
Each periodic signal can be can be described as a sum of **sine** and **cosine** functions. **Frequency** of each **sine** and **cosine** functions are integer product of frequencies of the original signal. The **phase** and **amplitude** of each harmonic element (sine and cosine) can be attained by **Fourier decomposition** (calculation of coefficients $a_{n}$ and $b_{n}$). Fourier series allows us to describe the original periodical signal as a sum of sine and cosine functions as:
$$
f(t) = a_{0} + \sum_{n=1}^{N} a_{n} \cos(n\omega_{0}t) +  \sum_{n=1}^{N} b_{n} \sin(n\omega_{0}t)
$$
$$
a_{0} = \frac{1}{2\pi}\int_{-\pi}^{\pi} f(x)dx
$$
$$
a_{n} = \frac{1}{\pi} \int_{-\pi}^{\pi} f(x)\cos(nx)dx
$$
$$
b_{n} = \frac{1}{\pi} \int_{-\pi}^{\pi} f(x)\sin(nx)dx
$$

$$
a_{0} = \frac{2}{T}\int_{-\pi}^{\pi} f(x)dx
$$
$$
a_{t} = \frac{2}{T} \int_{-\pi}^{\pi} f(x)\cos(tx)dx
$$
$$
b_{t} = \frac{2}{T} \int_{-\pi}^{\pi} f(x)\sin(tx)dx
$$
A Fourier series can be also be written as a sum of complex exponentials.
- **Input** is a **continuous periodic signal** (function).
- **Output** is a set of coefficients that designate **amplitudes** and **phases** using complex exponentials on multiples of the fundamental frequency (discrete values). From these coefficients we can then reconstruct the original signal using the **Fourier series**.
An important thing to keep in mind is that a **Fourier series** represents the same signal, but we only need the **coefficients**, which give us the information about its **spectrum**. A general equation for a **Fourier series** is:
$$
x(t) = \sum_{k\ = -\infty}^{\infty} c_{k} e^{j \ k \ \omega_{1} \ t} 
$$
A general equation for coefficients is:
$$
c_{k} = \frac{1}{T_{1}} \int_{T_{1}} x(t) e^{-j \ k \ \omega_{1} \ t} dt 
$$
### Discrete Fourier Series
Discrete Fourier series is created through a finite amount of sum of sine and cosine functions. It is an approximation of a Fourier series. The signal still **has to be periodic**. It allows us to do calculations in practice as computers are never continuous and it cannot do infinite calculations.
- **Input** is a **discrete periodic** signal with period **N**.
- **Output** are coefficients of that signify the **amplitude** and **phase** of the complex exponent on multiples of of the base frequency that periodically repeat themselves with a period **N**.
The sequence can be described as:
$$
x[n] = \sum_{k = 0}^{N-1} X[k]e^{jk \frac{2\pi}{N}n}
$$
Where the coefficients are:
$$
X[k] = \sum_{n=0}^{N-1}x[n]e^{-jk\frac{2\pi}{N}n}
$$
## Transformations
### Fourier Transform (FT)
Generalization of a **Fourier Series** for non-periodic signals. It is used to transform signals from **space or time** planes into a **frequency** plane. It allows us to decompose a signal into its corresponding frequencies, that make up the original signal.
- **Input** is a general continuous signal that does not have to be periodic.
- **Output** is a series of complex numbers, from which each corresponds to one frequency. The complex number is made of **amplitude** (the real component) and **phase** (the imaginary component) of the frequency **spectrum**. It can be sometimes used to decompose **Fourier Series** if it contains one period. 
$$
S(w) = \int_{-\infty}^{\infty} s(t)e^{-iwt} \, dt 
$$
### Discrete Time Fourier Transform (DTFT)
Generalization of the **Discrete Fourier Series** for non periodic signals. It is used to transform discrete signals from a **space or time** planes into a **frequency** plane.
- **Input** is a infinite amount of samples of a general discrete signal that does not have to be periodic.
- **Output** is a **continuous periodic function** in the **frequency** plane, which is not useable on a computer. **Discrete** is only in case of a periodic signal.
$$
X_{2\pi}(\omega) = \sum_{-\infty}^{\infty} x[n]e^{-j \omega n}
$$
### Discrete Fourier Transform (DFT)
It is used to transform a signal from a a **space or time** planes into a **frequency** plane. It samples **Discrete Time Fourier Transform (DTFT)** which is continuous. It runs with quadratic [[Time and Space Complexity| time complexity]].
- **Input** is **N** samples of a general non-periodic signal and treats that as periodic by N samples.
- **Output** is **N** **complex coefficients** (exponentials) that describe **amplitude** (the real component) and **phase** (the imaginary component) of the frequency **spectrum**. For computers this is an ideal situation.
$$
X_{k} = \sum_{n = 0}^{N-1} x_{n} e^{-jk\frac{2\pi}{N}n} = \sum_{n = 0}^{N-1} x_{n} [\cos(\frac{2\pi}{N}kn) - i \sin(\frac{2\pi}{N}kn)]
$$
### Fast Fourier Transform (FFT)
Modification of **Discrete Fourier Transformation** that is quicker and works with linearitmical [[Time and Space Complexity|time complexity]]. It can only calculate for samples that are equal to **2<sup>n</sup>**. Today it is one of the **most used algorithms ever**. It is used for:
- **Compression** like in JPEG, MP3 where the princip is that based on the **FFT** output spectrum it will eliminate most of the frequencies that are only represented minimally (which can be even up to **99%**). This is a loss compression, but a necessary one.
- **Derivation**
- **Data Filtration** where using **FFT** we can find frequencies that create noise and eliminate them.
- **Convolution** where using **FFT** we can transform a signal, multiply it and then transform it back using **iFFT** (inverse FFT). Normal convolution is quadratic, but this can be linearitmical.
## Tip
It applies that **periodical behaviour in time** makes **discrete behaviour in frequency** and **discrete behaviour in time** makes **periodical behaviour in frequency**. 
- **Fourier Series** is periodical continuous and its coefficients are discrete and non-periodical.
- **Discrete Time Fourier Series** is periodical discrete and its coefficients are discrete and periodical.
- **Fourier Transform** is non-periodical continuous and its coefficients are continuous and non-periodical.
- **Discrete Time Fourier Transform** is non-periodical discrete and its coefficients are continuous and periodical.
- **Discrete Fourier Transform** is pseudo-periodical discrete and its coefficients are discrete and periodical, but there is always the same amount of them as in the time.
## Useful Signals
- **Several Cosine Functions** where we can obtain coefficients from a specific formula:
$$
x(t) = 3 + 2 \cos(2000\pi t) + 1 \cos\left( 4000\pi t + \frac{\pi}{2} \right) + 3 \cos\left( 6000\pi t - \frac{\pi}{3} \right)
$$
$$
c_{k} = \frac{C_{k}}{2} e^{jk\psi}; c_{-k} = \frac{C_{k}}{2} e^{-jk\psi};
$$
- **Recatangular** where for impulse size **D = 6**, base period **T1 = 1μs**, and the pulse lengh **ϑ = 0.5 μs**. **ω = 2π/ϑ = 2π/(0.5×10−6) = 4π × 10−6 = 4Mπ. ω = 4Mπ**.
- **Dirac Impuls** is a theoretical impulse that in 0 second goes to infinity and back.
## Frequency
- **Normal non-normalized** frequency - f \[Hz\]
- **Normal normalized** frequency - f / Fs \[-\]
- **Circular non-normalized** frequency - ω = 2 * pi * f \[rad/s\]
- **Circular normalized** frequency - ( 2 * pi * f ) / Fs \[rad\]