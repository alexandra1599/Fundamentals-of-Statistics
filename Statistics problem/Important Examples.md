## 📌 Example: **IMPORTANT!!**

Let  $X_1, \dots, X_n \text{iid with density} \quad f(x) = e^{-(x - a)} \cdot \mathbb{1}_{\{x \ge a\}} \quad \text{for } a \in \mathbb{R}$  

This is a **shifted exponential** distribution: Exp(1) shifted by a

The indicator function implies:  
- f(x) = 0 for x < a  
- $f(x) = e^{-(x - a)}$ for $x \ge a$

---

### 👉 So here we have:
- $\lambda = 1$
- a is the **shift parameter**

---

### 🔹 (a) Find an estimator $\hat{a}$ for the shift parameter a

1) Consider the sample mean: $\bar{X}_n = \frac{1}{n} \sum X_i$

By the Law of Large Numbers (LLN): $\bar{X}_n \xrightarrow{P} \mathbb{E}[X_i]$

---

### ❗ Compute $\mathbb{E}[X]$:

$\mathbb{E}[X_1] = \int_{-\infty}^{\infty} x \cdot f(x) dx = \int_a^{\infty} x \cdot e^{-(x - a)} dx$

Make a substitution $u = x - a \Rightarrow x = u + a$ , so:
$\mathbb{E}[X_1] = \int_0^{\infty} (u + a) \cdot e^{-u} du = \int_0^{\infty} u e^{-u}du + a \int_0^{\infty} e^{-u}du$

$\mathbb{E}[X_1] = 1 + a$

Thus, $\mathbb{E}[X_1] = a + 1 \Rightarrow \hat{a} = \bar{X}_n - 1 \xrightarrow{P} a$

---

### 🔹 (b) Determine the distribution of $\hat{a}$

By the **Central Limit Theorem (CLT)**:

$\sqrt{n} \cdot \frac{\bar{X}_n - \mu}{\sigma} \xrightarrow{d} \mathcal{N}(0, 1)$

Where:

- $\mu = \mathbb{E}(X_1) = a + 1$
- $\sigma = \sqrt{\mathrm{Var}(X_1)}$
$\mathrm{Var}(X_1) = \mathbb{E}(X^2) - \mathbb{E}(X)^2$

$\mathbb{E}(X^2) = \int_a^\infty x^2 e^{-(x - a)} dx$

Let’s simplify using substitution:

Let $u = x - a \Rightarrow x = u + a$
$\mathbb{E}(X^2) = \int_0^\infty (u + a)^2 e^{-u}du = \int_0^\infty (u^2 + 2au + a^2) e^{-u} du$

Break it into parts:
$= \int_0^\infty u^2 e^{-u}du + 2a \int_0^\infty u e^{-u}du + a^2 \int_0^\infty e^{-u}du$

---

These integrals are standard:

- $\int_0^\infty u^2 e^{-u}du = 2$
- $\int_0^\infty u e^{-u}du = 1$
- $\int_0^\infty e^{-u}du = 1$

So: $\mathbb{E}(X^2) = 2 + 2a + a^2$

---

Then: $\mathrm{Var}(X_1) = \mathbb{E}(X^2) - (a + 1)^2 = 2 + 2a + a^2 - (a^2 + 2a + 1) = 1$

---

### ✅ Final result: Asymptotic Distribution of $\hat{a}$

From the Central Limit Theorem :

$\frac{\sqrt{n}}{1} (\bar{X}_n - (a + 1)) \xrightarrow{d} \mathcal{N}(0, 1)$

Which simplifies to:

$\sqrt{n} (\hat{a} - a) \xrightarrow{d} \mathcal{N}(0, 1)$

So: $\hat{a} - a \xrightarrow{d} \mathcal{N}\left(0, \frac{1}{\sqrt{n}}\right)$

Therefore, the estimator itself is asymptotically normal:

$\hat{a} \xrightarrow{d} \mathcal{N}\left(a, a+\frac{1}{\sqrt{n}}\right)$

## 📌 Confidence Interval for a based on $\hat{a}$

We want to compute the confidence interval:

$I = [\hat{a} - s, \hat{a} + s], \quad s > 0$

such that:

$\mathbb{P}(a \in I) = 1 - \alpha \Rightarrow \mathbb{P}(a \in [\hat{a} - s, \hat{a} + s]) = 1 - \alpha$

This implies:

$\hat{a} - s \le a \le \hat{a} + s \Rightarrow -s \le a - \hat{a} \le s \Rightarrow -\sqrt{n} s \le \sqrt{n}(\hat{a} - a) \le \sqrt{n} s$

By asymptotic normality:

$\mathbb{P}\left(a \in [\hat{a} - s, \hat{a} + s]\right) \xrightarrow{d} \mathbb{P}\left(Z \in [-\sqrt{n}s, \sqrt{n}s]\right), \quad Z \sim \mathcal{N}(0, 1)$

We want this probability to equal $1 - \alpha$:

$\mathbb{P}(Z \in [-\sqrt{n}s, \sqrt{n}s]) = 2 \Phi(\sqrt{n}s) - 1 = 1 - \alpha \Rightarrow \Phi(\sqrt{n}s) = 1 - \frac{\alpha}{2} \Rightarrow \sqrt{n}s = q_{\alpha/2}$

---

### ✅ Final Confidence Interval:

$I = \left[ \hat{a} - \frac{q_{\alpha/2}}{\sqrt{n}} ; \hat{a} + \frac{q_{\alpha/2}}{\sqrt{n}} \right]$
