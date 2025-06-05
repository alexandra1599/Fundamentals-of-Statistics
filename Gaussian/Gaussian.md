# Gaussian Distribution

A random variable X that follows a Gaussian/Normal distribution with mean $E[X] = \mu$ and variance $Var[X] = \sigma^2$ is denoted as 

**X ~ N($\mu,\sigma^2$)**

**Gaussian PDF :** f(x) = $\frac{1}{\sqrt{2\pi\sigma^2}} * e^{-\frac{(x-\mu)^2}{2\sigma^2}}$

As the variance increases, the PDF curve is more spread around the mean. The tail decays really fast in finite interval.

**Gaussian CDF :** No closed form. 

$F_{\mu,\sigma^2}(x) = P(X \leq x) = \phi(x) = \frac{1}{\sigma\sqrt{2\pi}} \int_{-\infty}^x e^{-\frac{(t - \mu)^2}{2\sigma^2}} \ dt$

If X ~ N($\mu,\sigma^2$) and Y = aX + b is another random variable with constants a and b, we get Y ~ N($a\mu+b,a^2\sigma^2$)

***Standardization / Normalization / Z-score :***

X ~ N($\mu,\sigma^2$) then 

$Z = \frac{X-\mu}{\sigma}$ ~ N(0,1)

$P(u \leq X \leq v) = P(\frac{u-\mu}{\sigma} \leq Z \leq \frac{v-\mu}{\sigma})$

***Symmetry :***

If X ~ N($0,\sigma^2$) then -X ~ N($0,\sigma^2$) and $1 - \phi(-z) = \phi(z)$

$P(|X| > x) = P(X > x) + P(X < -x) = P(X > x) + P(-X > x) = 2P(X > x)$ if x>0

***Quantiles :***

***Note :*** Percentile is quantile expressed in %

Let $\alpha \in (0,1)$. The **quantile** of order **$1-\alpha$** of a random variable X is the number $q_{\alpha}$ such that :

$P(X \leq q_{\alpha}) = 1-\alpha$

***Note :*** If $\alpha = 0.1$ then $q_{\alpha}$ is the $90^{th}$ percentile

Let F denote the CDF of X :
- $F(q_{\alpha}) = 1-\alpha$
- $q_{\alpha} = F^{-1}(1-\alpha)$
- $P(X > q_{\alpha}) = \alpha$
- $P(|X| > q_{\frac{\alpha}{2}}) = \alpha$
- $P(|Z| > q_{\alpha}) = 2\alpha$

