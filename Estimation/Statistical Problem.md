# Statistical Problem : The "T" (train)

You observe the times (in minutes) between arrivals of the T : $T_1, ..., T_n$

You assume these times are : 
- Mutually independent
- Exponential r.v with common parameter

You want to estimate the value of $\lambda$ based on the observed arrival times.

Memoryless Property of exponential r.v : $P(T > t+s | T > t) = P(T > s)$ for all $s,t \geq 0$

## Estimator

Density of $T_1$ : f(t) = $\lambda e^{-\lambda t}$

E($T_1$) = $\frac{1}{\lambda}$

Var($T_1$) = $\frac{1}{\lambda^2}$

**Natural Estimator of $\frac{1}{\lambda}$ is** 

$\bar{T}_n = \frac{1}{n} \sum{T_i} \to \frac{1}{\lambda}$ (a.s and P)

**Natural Estimator of $\lambda$ is** 

$\hat{\lambda} = \frac{1}{\bar{T}_n} \to \lambda$ (a.s and P)

Note : $E(\frac{1}{T_n}) > \frac{1}{E(T_n)}$

By CLT :

$\sqrt{n}(\bar{T}_n - \frac{1}{\lambda}) \to N(0,\lambda^{-2})$

How does this translate to $\hat{\lambda}$ ? How to find asymptotic CI for $\lambda$ ? $\to$ **Delta Method**

$bias(\frac{1}{\bar{X}_n}) = E(\frac{1}{\bar{X}_n}) - \lambda =  E(\frac{1}{\bar{X}_n}) - \frac{1}{E(X_i)} = E(\frac{1}{\bar{X}_n}) - \frac{1}{E(\bar{X}_n)}$

## Delta Method 

Let $(Z_n)_{n \geq 1}$ be a sequence of r.v such that 

$\sqrt{n}(Z_n - \theta) \to N(0,\sigma^2)$ in distribution for some $\theta \in R$ 

$Z_n$ is asymptotically normal around $\theta$.

Let g : R $\to$ R be continuously differentiable at $\theta$.

$(g(Z_n))_{n \geq 1}$ is also asymptotically normal around $g(\theta)$.

$\sqrt{n}(g(Z_n) - g(\theta)) \to N(0,g'(\theta)^2\sigma^2)$ in distribution 

**Consequences :** 

- $\hat{\lambda} = \frac{1}{\bar{X}_n}$
- $Var(\hat{\lambda}) = (g'(\frac{1}{\lambda}))^2 Var(\bar{X}_n)$
- $\sqrt{n}(\hat{\lambda} - \lambda) \to N(0,\lambda^2)$
- For $\alpha \in (0,1)$, when $n \to$ infinity : $|\hat{\lambda} - \lambda| \leq \lambda \frac{q_{\alpha/2}}{\sqrt{n}}$ with probability 1 - $\alpha$
- Asymptotic CI for $\lambda$ :
  1) $I_{solve} = [\hat{\lambda}(1 + \frac{q_{\alpha/2}}{\sqrt{n}})^{-1}, \hat{\lambda}(1 - \frac{q_{\alpha/2}}{\sqrt{n}})^{-1}]$
  2) $I_{plug-in} = [\hat{\lambda}(1 - \frac{q_{\alpha/2}}{\sqrt{n}}), \hat{\lambda}(1 + \frac{q_{\alpha/2}}{\sqrt{n}})]$
 
Let $X_1, ..., X_n$ ~ exp($\lambda$) :

$\hat{\lambda}_n = \frac{n}{\sum{X_i}}$ denotes an estimator of $\lambda$

$\hat{\lambda}_n$ is a **consistent** and **asymptotically normal** estimator of $\lambda$

![formula](https://latex.codecogs.com/png.image?\dpi{120}%20\lambda%20\in%20\left(%20\hat{\lambda}_n%20-%20\frac{q_{\alpha/2}%20\cdot%20\lambda}{\sqrt{n}},%20\hat{\lambda}_n%20+%20\frac{q_{\alpha/2}%20\cdot%20\lambda}{\sqrt{n}}%20\right))

with probability 1 - $\alpha$. Call this interval I. I is **NOT** a CI for $\lambda$ since the endpoints of I depend on the true parameter $\lambda$

We can use the conservative method to find a CI $I_{cons}$ for $\lambda$ defined by :

![I_cons](https://latex.codecogs.com/png.image?\dpi{120}&space;I_{\text{cons}}&space;:=&space;\left[&space;\hat{\lambda}_n&space;-&space;\max_{\lambda\in(0,\infty)}&space;\frac{q_{\alpha/2}&space;\cdot&space;\lambda}{\sqrt{n}},&space;\hat{\lambda}_n&space;+&space;\max_{\lambda\in(0,\infty)}&space;\frac{q_{\alpha/2}&space;\cdot&space;\lambda}{\sqrt{n}}&space;\right])

Since $\lambda \in (0, \infty)$, we have:

$$\max_{\lambda \in (0, \infty)} \frac{q_{\alpha/2} \cdot \lambda}{\sqrt{n}} = \infty$$

So, $I_{\text{cons}} = (-\infty, \infty)$


### Example

Let $X_1, ..., X_n$ ~ exp($\lambda$), with $\lambda > 0$

E(X) = $\frac{1}{\lambda}$. By CLT we have $sqrt{n}(\frac{1}{n} \sum{X_i} - \frac{1}{\lambda}) \to N(0, \sigma^2)$

$\sigma^2 = \frac{1}{\lambda^2}$

Set g(x) = 1/x

$\sqrt{n}(g(\frac{1}{n} \sum{X_i}) - g(\frac{1}{\lambda})) \to N(0, \tau^2)$

where $\tau^2$ is the asymptotic variance

$\tau^2 = g'(E(X_i))^2 Var(X_i) = g'(\frac{1}{\lambda})^2 \frac{1}{\lambda^2} = \lambda^2$ 
