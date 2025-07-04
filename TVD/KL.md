# Estimation Strategy : Kullback-Leibler (KL) Divergence

The KL divergence between two probability measures $P_{\theta}$ and $P_{\theta_1}$ is defined by :

- $KL(P_{\theta},P_{\theta_1}) = \sum_{x \in E} p_{\theta}(x) log(\frac{p_{\theta}(x)}{p_{\theta_1}(x)})$ if E is **discrete**
- $KL(P_{\theta},P_{\theta_1}) = \int_{E} f_{\theta}(x) log(\frac{f_{\theta}(x)}{f_{\theta_1}(x)}) dx$ if E is **continuous**

1) $KL(P_{\theta},P_{\theta_1}) ≠ KL(P_{\theta_1},P_{\theta})$
2) $KL(P_{\theta},P_{\theta_1}) \geq 0$
3) If $KL(P_{\theta},P_{\theta_1}) = 0 \rightarrow P_{\theta} = P_{\theta_1}$
4) $KL(P_{\theta},P_{\theta_1}) ≰ KL(P_{\theta},P_{\theta_2}) + KL(P_{\theta_2},P_{\theta_1})$

## Optimization Problem 

$\min KL(P_{\theta^{\*}},P_{\theta})$

There is a **unique** minimizer, i.e if m is the minimum value of $KL(P_{\theta^{\*}},P_{\theta})$ there is only one value 
$\theta_{min}$ such that $m = KL(P_{\theta^{\*}},P_{\theta_{min}})$

Here : $\theta_{min} = \theta^{\*}$

Weakly consistent estimator for $E_{\theta^{\*}}(ln p_{\theta}(X)) = \sum_{x \in E} p_{\theta^{\*}} ln p_{\theta}(x)$ is :

$\frac{1}{n} \sum ln(p_{\theta}(X_i))$
