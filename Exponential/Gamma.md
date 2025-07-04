# Gamma Distribution 

- Gamma($\alpha, \beta$), $\alpha > 0, \beta > 0$

- $f_{\alpha,\beta}(x) = \frac{\beta^{\alpha}}{\Gamma(\alpha)} x^{\alpha-1}e^{-\beta x}$ where $\frac{\beta^{\alpha}}{\Gamma(\alpha)}$ 
is the normalization constant.

- $\Gamma(s) = \int x^{s-1}e^{-x} dx$

- $\int_0^∞ f_{\alpha,\beta}(x) dx = 1$

- $X_1, ..., X_n$ are iid gamma variables with $\beta = \frac{1}{\alpha}$ for some $\alpha > 0$
  So $X_1, ..., X_n$ ~ Gamma($\alpha, \frac{1}{\alpha}$)

- $f_{\alpha}(x)  = \frac{1}{\Gamma(\alpha) \alpha^\alpha}  x^{\alpha-1}e^{-x/\alpha}$

- $\bar{X}_n = \frac{1}{n} \sum {X_i} \rightarrow E(X_i) = \alpha^2$ in probability

- X ~ Gamma($\alpha, \beta$) : E(X) = $\frac{\alpha}{\beta}$ and Var(X) = $\frac{\alpha}{\beta^2}$

- $\bar{X}_n \rightarrow \alpha^2$ in probability

- An estimator $\hat{\alpha}$ of $\alpha$ is $\hat{\alpha} = \sqrt{\bar{X}_n}$

- For the delta-method to apply, g(.) needs to be continuously differentiable at $\alpha^2$
  $\bar{X}_n \rightarrow N(\mu,\frac{\sigma^{2}}{n})$
  
  $\bar{X}_n \rightarrow N(\alpha^2,\frac{\alpha^{3}}{n})$
  
  g(x) = $\sqrt{x} \rightarrow g'(x) = \frac{1}{2\sqrt{x}}$
  
  $g'(\alpha^2) = \frac{1}{2\alpha}$
  
  $V(\hat{\alpha}) = (\frac{1}{2\alpha})^{2}\alpha^3 = \frac{\alpha}{4}$

- 90% confidence interval $(n=25, \bar{X}_n = 4.5)$ :
  
  $q_{\alpha/2} = q_{0.05} = 1.6448$
  
  $\hat{\alpha} = \sqrt{\bar{X}_n} = \sqrt{4.5} = 2.1213$

  $I_{plugin} = (\hat{\alpha} - \frac{q_{0.05}}{\sqrt{n}} \sqrt{V(\hat{\alpha})}, \hat{\alpha} + \frac{q_{0.05}}{\sqrt{n}} \sqrt{V(\hat{\alpha})})$
  
