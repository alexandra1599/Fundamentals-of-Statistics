# CDF and PDF

## Continuous Random Variable 

**CDF :** $F_X(x) = P(X \leq x) = \int_{-\inf}^x f_X(t)dt$

**PDF :** $\frac{dF_X(x)}{dx} = f_X(x)$

$\int_{-\inf}^{inf} f_X(x)dx = 1$

$P(a \leq X \leq b) = \int_a^b f_X(x)dx$

## Discrete Random Variable 

**CDF :** $F_X(x) = P(X \leq x) = \sum_{-inf}^x p_X(t)$

**PDF :** $\frac{dF_X(x)}{dx} = f_X(x)$

$\sum_x p_X(x)dx = 1$

$P(X \in A) = \sum_{X \in A} p_X(x)$

***Note :*** $lim (1-\frac{t}{n})^n = e^{-t}$
