# Total Variance Distance (TVD)

Let $(E, (P_{\theta})_{\theta \in O})$ be a statistical model associated with a sample of iid random variables $X_1, ..., X_n$

Assume that there exists $\theta^{\*} \in O$ such that $X_1$ ~ $P_{\theta^{\*}} : \theta^{\*}$ is the true parameter 

**Statistician's goal :** Given $X_1, ..., X_n$, find an estimator $\hat{\theta} = \hat{\theta}(X_1, ..., X_n)$ such that $P_{\hat{\theta}}$ is close to $P_{\theta^{\*}}$ for the 
true parameter $\theta^{\*}$. 

- $\|{P_{\hat{\theta}}(A) - P_{\theta^{\*}}(A)}\|$ is **small** for all $A \in E$

The **Total Variance Distance** between two probability measures $P_{\theta}$ and $P_{\theta_1}$ is defined by : 

- $TV(P_{\theta},P_{\theta_1}) = max_{A \in E} |{P_{\theta}(A) - P_{\theta_1}(A)}\|$

## TVD between Discrete measures

Assume E is **discrete** (finite, countable). This includes Bernouilli, Binomial, Poisson, ...

Therefore X has PMF : $P_{\theta}(X=x) = p_{\theta}(x)$ for all $x \in E$, $p_{\theta}(x) \leq 0$ and $\sum  p_{\theta}(x) = 1$

If two probability distributions are the same they have the same PMF. So the distance between the two random variables is equal to the distance between their two PMFs. 

The TVD between $P_{\theta}$ and $P_{\theta_1}$ is a simple function of the PMFs :

- $TV(P_{\theta},P_{\theta_1}) = \frac{1}{2} \sum_{x \in E} \|p_{\theta}(x) - p_{\theta_1}(x) \|$

Note : $P_{\theta}(A^{C}) - P_{\theta_1}(A^{C}) = P_{\theta_1}(A) - P_{\theta}(A)$

## TVD between Continuous measures

Assume E is **continuous**, X has density $P_{\theta}(X \in A) = \int_{A} f_{\theta}(x) dx$ for all $A \in E$ 

$f_{\theta}(x) \geq 0$ and $\int_{E} f_{\theta}(x)dx = 1$

The TVD between $P_{\theta}$ and $P_{\theta_1}$ is a simple function of $f_{\theta}$ and $f_{\theta_1}$ :

- $TV(P_{\theta},P_{\theta_1}) = \frac{1}{2} \int \|f_{\theta}(x) - f_{\theta_1}(x) \| dx$

## Properties of TVD

1) $TV(P_{\theta},P_{\theta_1}) = TV(P_{\theta_1},P_{\theta})$
2) $TV(P_{\theta},P_{\theta_1}) \geq 0$ , $TV(P_{\theta},P_{\theta_1}) \leq 1$
3) If $TV(P_{\theta},P_{\theta_1}) = 0 \rightarrow P_{\theta} = P_{\theta_1}$
4) $TV(P_{\theta},P_{\theta_1}) \leq TV(P_{\theta_1},P_{\theta_2}) + TV(P_{\theta_2},P_{\theta_1})$

