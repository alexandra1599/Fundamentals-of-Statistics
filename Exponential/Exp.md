# Exponential Random Variable 

X ~ Exp($\lambda$)

Sample space : [0, inf)

PDF : $f_X(x) = \lambda e^{-\lambda x}$

CDF : $F_X(x) = 1 - e^{-\lambda x}$

E[X] = $\frac{1}{\lambda}$

Var[X] = $\frac{1}{\lambda^2}$

$E[X^2] = \frac{2}{\lambda^2}$

$E[X^n] = \frac{n!}{\lambda^n}$

$P(X \geq a) = 1 - P(X < a) = 1 - F_X(a)$

$P(X > a) = e^{-\lambda a}$

## Memoryless Property 

$P(X \geq k+a | X \geq a) = P(X \geq k) = e^{-\lambda k}$
