Analyses a **response** of a system to an impulse. Discrete impulse is defined as:
$$
\delta[n] = 1 \ \ \ n=0; 0 \ \ n n\neq 0
$$
Any [[Signal#Discrete| Discrete Signal]]  can be represented by a weighted sum of shifted (phased) discrete impulses in time. Impulse response **defines LTI** systems and uses convolution. Impulse response defines the system because impulse contains all of the frequencies (**in frequency domain is equal to 1 for all f**).
## Convolution
A basic operation using two signals and is defined be equation:
$$
(f * g)[n] = \sum_{m = -\infty}^{\infty} f[m]g[n-m]
$$
$$
(f * g)[n] = \sum_{m = -\infty}^{\infty} f[n-m]g[m]
$$
For an example:
$$
y[n] = \sum_{k = -\infty}^{\infty} x[k]h[n-k]
$$
With **h** having values **1** in times **{0, 1, 2}** and **x** having values of **1/2** in 0 and **2** in **1**.
$$
y[-1] = x[0]h[-1] + x[1]h[-2] = \frac{1}{2} \times 0 + 2x \times 0 = 0 
$$
$$
y[0] = x[0]h[0] + x[1]h[-1] = \frac{1}{2} \times 1 + 2x \times 0 = \frac{1}{2} 
$$
Which can go on and on till infinity. In **frequency domain** these two signal can be just **multiplied together**.
### Types
- **Finite Impulse Response (FIR)** means that the impulse response of a finite input will have a finite length. These filters cannot have even one loop back (cannot use output).
$$
y[n] = \sum_{k = 0}^{n} b_{k}x[n-k]
$$
- **Infinite Impulse Response (IIR)** the impulse response to a finite input has an infinitely long length. These filters must have at least one loop back (at least once use an output).
$$
y[n] = \sum_{k = 0}^{n} b_{k}x[n-k] - \sum_{k = 1}^{n} a_{k}y[n-k]
$$