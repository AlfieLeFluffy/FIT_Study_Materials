---
tags:
  - MSP
aliases:
  - fisher information
---
## Definition
If the [[Likelihood#Regularity Condition|Regularity Conditions]] hold then the integral $$J_{n}(\theta)=\int_{M}\left[ \frac{f'(x,\theta)}{f(x,\theta)} \right]^2f(x,\theta)dx$$ is called the Fished information. Alternative forms of the Fisher information are $$J_{n}(\theta)=\int_{M}\left[ \frac{dl(\theta)}{d\theta} \right]^2f(x,\theta)dx=E\left[ \frac{dl(\theta)}{\theta} \right]^2$$ If regularity conditions 3 and 4 can be extended to second derivates, the the Fished information can be computed as follows: $$J_{n}(\theta)=-E\left[ \frac{d^2l(\theta)}{d\theta^2} \right]$$
Let $X_{1},\dots,X_{n}$ be independent identically distributed variables fulfilling regularity conditions, than Fisher information of the sample can be expressed as: $$J_{n}(\theta)=nJ(\theta)$$
In order to generalize Fisher information for a parameter vector it is necessary to:
- Expand the regularity conditions for derivatives between parameters.
- Take into account the possible dependence between parameters. Meaning there will be a Fisher information for all pairs of $i,j$ in a form:
- Hence instead of one value per parameter you get a Fisher information matrix, and positivity assumption on integral value needs to expanded to be positive defined matrix.