# Gamma Distribution 

Gamma($\alpha, \beta$), $\alpha > 0, \beta > 0$

$f_{\alpha,\beta}(x) = \frac{\beta^{\alpha}}{\Gamma(\alpha)} x^{\alpha-1}e^{-\beta x}$ where $\frac{\beta^{\alpha}}{\Gamma(\alpha)}$ 
is the normalization constant.

$\Gamma(s) = \int x^{s-1}e^{-x} dx$

$\int_0^∞ f_{\alpha,\beta}(x) dx = 1$

$X_1, ..., X_n$ are iid gamma variables with $\beta = \frac{1}{\alpha}$ for some $\alpha > 0$

So $X_1, ..., X_n$ ~ Gamma($\alpha, \frac{1}{\alpha}$)

$f_{\alpha}(x)  = \frac{1}{\Gamma(\alpha) \alpha^\alpha}  x^{\alpha-1}e^{-x/\alpha}$

$\bar{X}_n = \frac{1}{n} \sum {X_i} \rightarrow E(X_i) = \alpha^2$ in probability

X ~ Gamma($\alpha, \beta$) : E(X) = $\frac{\alpha}{\beta}$ and Var(X) = $\frac{\alpha}{\beta^2}$

$\bar{X}_n \rightarrow \alpha^2$ in probability

An estimator $\hat{\alpha}$ of $\alpha$ is $\hat{\alpha} = \sqrt{\bar{X}_n}$
