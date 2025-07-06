**Differential equation** represents equations of **an unknown order** and **their differences**. These are differential equations that are in discrete time. In general these equations look:
$$
y[n] = \sum_{k = 0}^{Q}b_{k}x[n-k] \  - \ \sum_{k = 1}^{P}a_{k}y[n-k] 
$$
Where:
- **x\[n - k\]** are current and delayed versions of the input.
- **y\[n - k\]** are delayed versions of the output.
Differential equations require **input conditions** (variables). Using differential equations we can describe **Linear Time-Invariant (LTI)** systems.
- **Linearity** must apply either addition and scaling or homogenity. 
- **Time-Invariant** means the system does **not change its behaviour** in time. If the system reacted to a signal **x** with output **y**, then it will react to the same signal **x** in ten seconds by the same signal **y**.
An example of such system can be: the current output $y[n]$ is defined as sum of previous output $\frac{1}{2}x[n-1]$, current input $\frac{1}{4}x[n]$ and previous input $\frac{1}{4}x[n-1]$. This can be reworked as:
$$
y[n] = \frac{1}{2}x[n-1] + \frac{1}{4}x[n] + \frac{1}{4}x[n-1]
$$
Another graphical example can be for the equation:
$$
y[n] = 4x[n] + \frac{1}{6}y[n-1] + \frac{1}{6}y[n-2]
$$
![[Differential_System_Example_1]]
Examples of a low pass filter:
$$
y[n] = \frac{1}{6} (x[n] + x[n-1] + x[n-2] + x[n-3] + x[n-4] + x[n-5])
$$
$$
y[n] = 0.95y[n-1] + 0.05x[n]
$$
Examples of high pass filter:
$$
y[n] = \frac{1}{6} (x[n] - x[n-1] - x[n-2] - x[n-3] - x[n-4] - x[n-5])
$$
$$
y[n] = - 0.95y[n-1] + 0.05x[n]
$$