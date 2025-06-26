# Estimation

What we want to do most times when we observe data that is well-defined and identifiable is find an estimator of it.

## Parameter Estimation Definitions

- Statistic : Any measurable function (can compute it exactly from data) of the sample (Ex : mean, variance, max, min, ... . Note : inf/sup are **NOT** measurable)
- Estimator of $\theta$ : Any statistic whos expression does not depend on $\theta$

1) An estimator $\hat{\theta}_n$ of $\theta$ is weakly (strongly) consistent if $\hat{\theta}_n \to \theta$ in probability (a.s.) w.r.t. $P\theta$
2) An estimator $\hat{\theta}_n$ of $\theta$ is asymptotically normal if $\sqrt{n}(\hat{\theta}_n - \theta) \to N(0,\sigma^2)$  where $\sigma^2$ is the asymptotic variance of $\hat{\theta}_n$

Note : Var($\hat{\theta}_n$) $\to$ 0

### Example 

Let $X_1, X_2, ..., X_n$ ~ i.i.d Ber(p), with $\bar{X}_n$ the estimator : $\bar{X}_n = \frac{1}{n}\sum{X_i}$

What is the smallest constant c such that $n^{c}(\bar{X}_n - p)$ does not converge to 0 ?

We know that $\sqrt{n}(\bar{X}_n - p) \to N(0,p(1-p))$ from CLT so c = 0.5. 

So we get : 
- $c < 0.5 \to$ converges to 0
- $c > 0.5 \to$ diverges

## Bias of an Estimator 

bias($\hat{\theta}_n$) = E($\hat{\theta}_n$) - $\theta$

If bias($\hat{\theta}_n$) = 0, we say $\hat{\theta}_n$ is unbiased (that is what we want!!)

Some biased estimators can still be bad so we need to check the variance.

### Example 

Assume $X_1, X_2, ..., X_n$ ~ i.i.d Ber(p), compute bias for :
1) $\hat{p}_n$ = $\bar{X}_n$ : bias($\hat{p}_n$) = E($\bar{X}_n$ ) - p = p - p = 0 $\to$ unbiased
2) $\hat{p}_n$ = $X_1$ : bias($\hat{p}_n$) = E($X_1$ ) - p = p - p = 0 $\to$ unbiased
3) $\hat{p}_n$ = $\frac{X_1+X_2}{2}$ : bias($\hat{p}_n$) = 0 $\to$ unbiased
4) $\hat{p}_n$ = $\sqrt{I(X_1=1,X_2=1)} \to$ $\hat{p}_n$ ~ Ber($p^2$) $\to bias(\hat{p}_n) = p^2 - p$

**NOTE** : 
1) An indicator function I is Bernouilli
2) $\sqrt{E(X)^2} \neq E(X)$\

## Jensen's Inequality

1) Function f(.) **convex** :

E(f(X)) $\geq$ f(E(X))

2) Function f(.) **concave** :

E(f(X)) $\leq$ f(E(X))


### Examples 

1) Let $X_1, X_2, ..., X_n$ ~ U([a,a+1]) where a is unknown
Let $\bar{X}_n = \frac{1}{n}\sum{X_i}$.

In terms of a, find E($\bar{X}_n$) : 

$E(\bar{X}_n) = E(\frac{1}{n}\sum{X_i}) = \frac{1}{n}E(\sum{X_i}) = \frac{1}{n}\sum{E(X_i)}$

$E(X_i) = \frac{a+a+1}{2} = a + 0.5$

$E(\bar{X}_n) = \frac{1}{n}\sum{a+0.5} = a + 0.5$

Compute bias($\bar{X}_n$) :

bias($\bar{X}_n$) = E($\bar{X}_n$) - a = a + 0.5 - a = 0.5


2) Let X be a positive r.v with expectation $\lambda$. How does $\mu = E(\frac{1}{X})$ compare to $\lambda$ ?

Let f(.) = $\frac{1}{.}$, so f(.) is a convex function in [0,inf] so by Jensen's inequality we get E(f(X)) $\geq$ f(E(X))

So $\mu \geq \frac{1}{\lambda}$


## Variance of an estimator

We want the **smallest variance** possible. An estimator is a r.v so we can get the variance.

### Example 

Assume $X_1, X_2, ..., X_n$ ~ i.i.d Ber(p)
1) $\hat{p}_n$ = $\bar{X}_n$ : Var($\hat{p}_n$) = $\frac{p(1-p)}{n}$
2) $\hat{p}_n$ = $X_1$ : Var($\hat{p}_n$) = p(1 - p) $\to$ worse than case 1
3) $\hat{p}_n$ = $\frac{X_1+X_2}{2}$ : Var($\hat{p}_n$) = $\frac{p(1-p)}{2}$
4) $\hat{p}_n$ = $\sqrt{I(X_1=1,X_2=1)} \to$ $\hat{p}_n$ ~ Ber($p^2$) $\to$ Var($\hat{p}_n$) = $p^{2}(1-p)^{2}$
5) $X_1, X_2, ..., X_n$ ~ U([a,a+1]), Var($\bar{X}_n$) = $\frac{1}{n}Var(X)$, Var(X) = $\frac{1}{12n}$

## Quadratic Risk

We want estimators to have **low bias AND low variance** at the same time. The **Risk** (Quadratic Risk) of an estimator $\hat{\theta}_n \in R$ is :

R($\hat{\theta}_n$) = $E(|\hat{\theta}_n - \theta|^2)$ = Var($\hat{\theta}_n$) + bias($\hat{\theta}_n)^2$

### Example 

$X_1, X_2, ..., X_n$ ~ U([a,a+1]). Find quadratic risk of $\bar{X}_n$ - 0.5

R($\bar{X}_n$ - 0.5) = Var($\bar{X}_n$ - 0.5) + bias($\bar{X}_n - 0.5)^2$

bias($\bar{X}_n - 0.5)^2$ = E($\bar{X}_n - 0.5$) - a = a + 0.5 - 0.5 - a = 0

R($\bar{X}_n$ - 0.5)  =  Var($\bar{X}_n$ - 0.5) = $\frac{1}{12n}$

### Note 

For any r.v X and constants a,b,c : 

1) Var(X+c) = Var(X)
2) Var(aX+b) = $a^2$Var(X)

## Consistency

Consistency implies $\hat{\theta}_n \to \theta$

So to ensure $\theta_n \to \theta$ in probability, $\hat{\theta}_n$ should be consistent and its quadratic risk should go to 0.
