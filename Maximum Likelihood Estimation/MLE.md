# Maximum Likelihood Estimation (MLE)

We define:

$$
\hat{\mathrm{KL}}(P_{\theta^*}, P_\theta) = \text{"constant"} - \frac{1}{n} \sum_{i=1}^n \log P_\theta(X_i)
$$

So,

$$
\min_{\theta \in \Theta} \hat{\mathrm{KL}}(P_{\theta^*}, P_\theta)
\iff
\min_{\theta \in \Theta} \frac{1}{n} \sum_{i=1}^n \log P_\theta(X_i)
$$

$$
\iff
\max_{\theta \in \Theta} \frac{1}{n} \sum_{i=1}^n \log P_\theta(X_i)
$$

$$
\iff
\max_{\theta \in \Theta} \log \left( \frac{1}{n} \sum_{i=1}^n P_\theta(X_i) \right)
$$

$$
\iff
\max_{\theta \in \Theta} \sum_{i=1}^n \log P_\theta(X_i)
$$

So finally:

$$
\min_{\theta \in \Theta} \hat{\mathrm{KL}}(P_{\theta^*}, P_\theta)
\iff
\max_{\theta \in \Theta} \prod_{i=1}^n P_\theta(X_i)
$$

---

# Likelihood: Discrete Case

Let $\mathcal{E}$ be a discrete space and $X_1, \ldots, X_n$ be i.i.d.

The **likelihood** of the model is the map $L_n$ such that:

$$
L_n : \mathcal{E}^n \times \Theta \rightarrow \mathbb{R}
$$

$$
(x_1, \ldots, x_n, \theta) \mapsto P_\theta(X_1 = x_1, \ldots, X_n = x_n)
$$

$$
= \prod_{i=1}^n P_\theta(X_i = x_i)
$$

---

## 1. Bernoulli

$$
L(x_1, \ldots, x_n, p) = \prod_{i=1}^n P_p(X_i = x_i)
= \prod_{i=1}^n p^{x_i} (1 - p)^{1 - x_i}
$$

Let $S = \sum x_i$ (total number of successes), then:

$$
L_n = p^S (1 - p)^{n - S}
$$

---

## 2. Poisson

$$
L(x_1, \ldots, x_n, \lambda) = e^{-n \lambda} \cdot \frac{\lambda^{\sum x_i}}{x_1! x_2! \cdots x_n!}
$$

## Likelihood: Continuous Case

Assume \( P_\theta \) has density \( f_\theta \).

$$
L_n : \mathbb{E}^n \times \Theta \to \mathbb{R}, \quad L_n(x_1, \dots, x_n, \theta) = \prod_{i=1}^n f_\theta(x_i)
$$

### 1. Gaussian

$$
L(x_1, \dots, x_n; \mu, \sigma^2) = \frac{1}{(\sigma \sqrt{2\pi})^n} \exp\left( -\frac{1}{2\sigma^2} \sum_{i=1}^n (x_i - \mu)^2 \right)
$$

### 2. Exponential

$$
L(x_1, \dots, x_n; \lambda) = \lambda^n \exp\left( -\lambda \sum_{i=1}^n x_i \right) \cdot \mathbb{1}_{\min x_i > 0}
$$

### 3. Uniform

$$
X_1, \dots, X_n \sim \text{Unif}[0, b], \quad b > 0
$$

$$
L(x_1, \dots, x_n; b) = \frac{1}{b^n} \cdot \mathbb{1}_{\max x_i < b}
$$

## Mixture of Gaussians

Let $$\( N(\mu_1, 1) \) and \( N(\mu_2, 1) \)$$ be mixed with weights $$\( \frac{1}{2} \) and \( \frac{1}{2} \)$$.

### Two Descriptions

**1. PDF**:

$$
f(x) = \frac{1}{2\sqrt{2\pi}} \left[ \exp\left( -\frac{(x - \mu_1)^2}{2} \right) + \exp\left( -\frac{(x - \mu_2)^2}{2} \right) \right]
$$

**2. Sampling**:

Let $$\( Z \sim \text{Bern}(\pi) \) or \( Z \sim \text{Bern}\left(\frac{1}{2}\right) \)$$

$$
X = Z \cdot X_1 + (1 - Z) \cdot X_2
$$

### Likelihood

Use the pdf formulation:

$$
L(x_1, \dots, x_n; \mu_1, \mu_2) = \prod_{i=1}^n f(x_i)
$$

### In General

$$
L(x_1, \dots, x_n; \mu_1, \mu_2, \sigma_1^2, \sigma_2^2, \pi^*) = \prod_{i=1}^n \left( \frac{\pi^*}{\sigma_1 \sqrt{2\pi}} \exp\left( -\frac{(x_i - \mu_1)^2}{2\sigma_1^2} \right) + \frac{1 - \pi^*}{\sigma_2 \sqrt{2\pi}} \exp\left( -\frac{(x_i - \mu_2)^2}{2\sigma_2^2} \right) \right)
$$



