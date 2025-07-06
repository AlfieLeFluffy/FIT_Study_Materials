A **signal** is intentional **physical phenomenon**, that **carries information** about some kind of an event. It is a time and space variable (**physical variable**).
## Types
### Continuous
Are present in the **real world** and have a value for each moment in time, which creates a continuous function. These signals can be represented by a function and we notate them as **x(t)**. The values of a continuous signal are in the set of real numbers.
### Discrete
Are represented as a set of instantaneous values with the time moving in **steps**. They can be store on **numeric computers**. We notate them as **x\[t\]** (the square brackets to indicate the time is discrete, like an array of numbers in programming) and gain values of set of whole numbers. The discrete signal also has a **finite amount of values**. To create a discrete signal from continuous signal we use **sampling**. This method first evaluates (measures) the values in each discrete time and then **quantize** them into a set of values for a given signal.
- **Sampling** uses periodic recording of the continuous signal. The period with which we sample a signal must be twice as small as the smallest signal we want to sample. This is also called a **Shannon's Theorem**.
- **Quantification** uses discretization of sampled values into a signal's value range (we convert from real number into whole numbers). This process is irreversible and looses data.
### Deterministic
Deterministic signals are such that for each **continuous time** or **discrete time** we can precisely **evaluate what will be the signals value**. They can be defined by a **function**.
### Random
The signal cannot be described by a function. For each continuous or discrete time we cannot evaluate it in advance. They are described by a a **mean value** and **dispersion**.
### Periodical
The signals progression repeats with a certain period. This means that value **s(t + T)** will be **s(t)** where **T** is the period offset.
#### Harmonic
The simplest periodical signal. They have the form $x(t) = A \times \cos(\omega t + \psi_{0})$, where:
- **A** is the amplitude or the maximum value of the periodic function.
- **ω** is the angle or circular frequency (rad/s) for a continuous signal or (rad) for discrete.
- **Ⲫ** is the starting phase (rad). This the offset on the X axis.