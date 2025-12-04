#IPT #MSP
We have two sets:
- **Base Set** (population) that contains all defined units.
- **Selective Set** (selection of population) that contains some of the define units.
Through **properties** of the **selective set** we can **generalize the entire base**. This is for example used in **election polling** where we use **1000 asked voters** through which we can **estimate the distribution for all 8 milion voters**.
### Point Estimation
An **unknown parameter** (for example the mean value) of the **base set** can be estimated using a single value (point) of the **selective set**. A point estimation of a parameter of the base set are the **describing characteristics of the selective set**. 
An example could be:
	If the unknown parameter of the base set is the average voltage on 10 000 new batteries, then we can select 200 batteries (selective set), measure the selective set and get the mean value from it.
A point estimation will nearly never be the true (correct) value of the unknown parameter. A  better estimation is such that has a distribution is more concentrated on the unknown parameter, in other words has a **lower distribution**, or more specifically **lower standard deviation**.
#### Unbiased Estimation
An estimation is unbiased if it does not undervalue or overvalue the true value of the parameter. It cannot guarantee a good estimation, but it can eliminate **systematic errors**. The selective mean and dispersion are unbiased if only the dispersion is unbiased.
#### Consistent Estimation
It is a good estimation that is getting close to the true value of the parameter with the increasing amount of observations we make.
#### Mean Square (Quadratic) Error
It allows us to measure the transference of the point estimation and it combines the **dispersion** and **deviation**. 
$$MSE = \frac{1}{n} \sum _{i=1}^{n}(X_{i} - average(X))^2$$
#### Selective Average
$$average(X_{n}) = \frac{1}{n} \sum_{i=1}^{n} X_{i}$$
#### Selective Dispersion
$$s^2 = \frac{1}{n-1} \sum _{i=1}^{n}(X_{i} - average(X))^2$$
### Interval Estimation
Because **Point Estimation** is quite inaccurate in practice **Interval Estimation** is commonly used. With interval estimation we can say with some probability (usually high) that the value of an unknown parameter is in an interval.
The reliability of a given estimation is given (selected) by the probability of the interval of reliability. The higher the interval is, the more reliable the estimation is. The more the estimation is accurate (reliable) the wider the interval will be. The wider the interval is, the more the estimation is reliable, but then it is less accurate, which is impractical. Between accuracy and reliability is an uneven relation.
An interval estimation of a [[normal distribution]] can be calculated as:
$$ CI = average(x) \pm z \times \frac{σ(X)}{\sqrt{ n }}$$
Where:
- **average(x)** is the average of the selective set.
- **z** is the confidence level read from a table using the percentage of how sure we want to be.
- **σ(X)** is the standard deviation.
- **n** is the sample size.