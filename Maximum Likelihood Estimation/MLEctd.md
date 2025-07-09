# MLE

Let $X_1, ..., X_n$ be iid random variables associated with $({E}, (P_{\theta})_{\theta \in \Theta})$ and L the corresponding likelihood.
The **maximum likelihood estimator** of $\theta$ is 

$\hat\theta_{n}^{MLE} = argmax_{\theta \in \Theta} L(X_1,...,X_n,\theta)$

## Log-likelihood estimator

$\hat\theta_{n}^{MLE} = argmax_{\theta \in \Theta} log L(X_1,...,X_n,\theta)$

## Bernouilli

$\hat{p}_{n}^{MLE} = \bar{X}_n$

I(p) = $\frac{1}{p(1-p)}$

$l(p) = X log(p) + (1-X) log(1-p)$

## Poisson

$\hat{\lambda}_{n}^{MLE} = \bar{X}_n$

I($\lambda$) = $\frac{1}{\lambda}$

## Gaussian

$\hat{\mu}_{n}^{MLE} = \bar{X}_n$

$\hat{\sigma}_{n}^2(p) = \frac{1}{n} \sum (X_i - \bar{X}_n)^2$

## Uniform

$\hat{\theta}_{n}^{MLE} = max X_i$

