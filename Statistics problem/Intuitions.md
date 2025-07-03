# Some notes on how to think in a problem 

If they ask $X_1, ..., X_n$ ~ N($\theta,\theta$), with $\bar{X}_n = \frac{1}{n}\sum X_i$.

E($\bar{X}_n$) = $\frac{1}{n}\sum E(X_i) = \theta$

Var($\bar{X}_n$) = $\frac{1}{n^2}\sum Var(X_i) = \frac{\theta}{n}$

So $\bar{X}_n$ ~ N($\theta,\frac{\theta}{n})$

1) Find the confidence interval $I_{\theta}$ such that P($\theta \in I_{\theta}$) = 0.9
   a) Let Z = $\frac{\bar{X}_n - \theta}{\sqrt{\frac{\theta}{n}}}$ ~ N(0,1)
   
   b) 1 - $\alpha$ = 0.9 $\rightarrow \alpha = 0.1 \rightarrow \frac{\alpha}{2} = 0.05$

   c) P($-q_{\alpha/2} \leq Z \leq q_{\alpha/2}$) = $P(-q_{\alpha/2}\sqrt{\theta/n} \leq \bar{X}_n - \theta \leq \sqrt{\theta/n}*q{\alpha/2})$

= $P(-q_{α/2} · \sqrt{\theta/n} + X_n ≤ \theta ≤ q_{α/2} · \sqrt{\theta/n} + X_n) = 0.9$

  d) I = ($\bar{X}_n - 1.6448\sqrt{\theta/n}, \bar{X}_n + 1.6448\sqrt{\theta/n}$)

  e) $I_{plugin} = (\bar{X}_n - 1.6448\sqrt{\bar{X}_n/n}, \bar{X}_n + 1.6448\sqrt{\bar{X}_n/n}$)



