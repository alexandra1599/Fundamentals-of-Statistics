# Estimation

What we want to do most times when we observe data that is well-defined and identifiable is find an estimator of it.

## Parameter Estimation Definitions

- Statistic : Any measurable function (can compute it exactly from data) of the sample (Ex : mean, variance, max, min, ... . Note : inf/sup are **NOT** measurable)
- Estimator of $\theta$ : Any statistic whos expression does not depend on $\theta$

1) An estimator $\hat{\theta}_n$ of $\theta$ is weakly (strongly) consistent if $\hat{\theta}_n \to \theta$ in probability (a.s.) w.r.t. $P\theta$  
